---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Word_Transformation
title: 단어 변환 (with.Java)
# title: Word Transformation (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, bfs]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-18 09:00:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

## 단어 변환 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

두 개의 단어 begin, target과 단어의 집합 words가 있습니다.

아래와 같은 규칙을 이용하여 begin에서 target으로 변환하는 가장 짧은 변환 과정을 찾으려고 합니다.

1. 한 번에 한 개의 알파벳만 바꿀 수 있습니다.
2. words에 있는 단어로만 변환할 수 있습니다. 예를 들어 begin이 "hit", target가 "cog", words가 ["hot","dot","dog","lot","log","cog"]라면 "hit" -> "hot" -> "dot" -> "dog" -> "cog"와 같이 4단계를 거쳐 변환할 수 있습니다.

두 개의 단어 begin, target과 단어의 집합 words가 매개변수로 주어질 때, 최소 몇 단계의 과정을 거쳐 begin을 target으로 변환할 수 있는지 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- 각 단어는 알파벳 소문자로만 이루어져 있습니다.
- 각 단어의 길이는 3 이상 10 이하이며 모든 단어의 길이는 같습니다.
- words에는 3개 이상 50개 이하의 단어가 있으며 중복되는 단어는 없습니다.
- begin과 target은 같지 않습니다.
- 변환할 수 없는 경우에는 0를 return 합니다.

#### 입출력 예

<!-- | operations                                                                  | return     |
| --------------------------------------------------------------------------- | ---------- |
| ["I 16", "I -5643", "D -1", "D 1", "D 1", "I 123", "D -1"]                  | [0,0]      |
| ["I -45", "I 653", "D 1", "I -642", "I 45", "I 97", "D 1", "D -1", "I 333"] | [333, -45] | -->

| begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      |

### 문제 풀이

```java
import java.util.Queue;
import java.util.LinkedList;
import java.util.ArrayList;

class Solution {
    public int solution(String begin, String target, String[] words) {
        int answer = 0;
        Queue<String> que = new LinkedList<>();
        ArrayList<String> list = new ArrayList<>();
        int check = 0;
        for(String str : words){
            list.add(str);
        }
        if(!list.contains(target)){
            return 0;
        }

        que.offer(begin);
        list.remove(begin);

        while(!que.isEmpty()){
            for(int i = 0; i < que.size(); i++){
                String temp = "";
                String current_str = que.poll();
                if(current_str.equals(target)){
                    return answer;
                }
                for(String str : list){
                     if(convert(current_str, str)){
                         que.offer(str);
                         temp = str;
                     }
                }
                list.remove(temp);
            }
            answer++;
        }

        return 0;
    }

    public boolean convert(String word_1, String word_2){
        int count = 0;
        for(int i = 0; i < word_1.length(); i++){
            if(word_1.charAt(i) != word_2.charAt(i)){
                count++;
            }
        }

        return count == 1;
    }
}
```

#### 풀이 설명

주어진 문제는 시작 문자열 begin에서 목표 문자열 target으로 변환하기 위해 최소한의 변환 횟수를 구하는 것입니다.

단, 변환 과정에서 각 단어는 미리 주어진 단어 목록(words)에 존재해야 하며, 각 단어는 한 번에 하나의 문자만 바뀔 수 있습니다.

문제를 해결하기 위해 Queue와 ArrayList를 사용한 BFS를 구현합니다.

BFS를 사용하여 begin 문자열에서 target 문자열로의 최단 경로를 찾습니다.

각 변환 단계에서 현재 단어와 다음 단어가 한 글자만 다른지 검사합니다.

변환 과정에서 목표 단어 target에 도달했는지 확인합니다.

초기화 단계에서 Queue<String> que는 BFS를 구현하기 위한 큐로 사용되고, ArrayList<String> list는 변환 가능한 단어 목록을 저장합니다.

answer 변수는 변환 횟수를 저장하는 데 사용됩니다. words 배열을 list로 변환하고 target 단어가 목록에 있는지 확인합니다.

만약 target이 목록에 없으면 변환할 수 없으므로 0을 반환합니다.

BFS 탐색 과정에서는 시작 단어 begin을 큐에 추가하고 리스트에서 제거합니다.

큐가 빌 때까지 반복하여 각 레벨의 모든 단어를 탐색합니다.

현재 단어와 변환 가능한 단어를 찾아 큐에 추가합니다. 변환된 단어는 리스트에서 제거하여 중복 탐색을 방지합니다.

목표 단어에 도달하면 변환 횟수를 반환합니다.

convert 메소드는 두 단어가 한 글자만 다른지 검사합니다.

두 단어의 각 문자를 비교하여 차이가 1인 경우 변환이 가능하므로 true를 반환합니다.

##### 결론

주어진 제약 조건 내에서 시작 문자열에서 목표 문자열로의 최소 변환 횟수를 BFS를 통해 효과적으로 찾을 수 있습니다.

이 과정에서 변환 가능성을 검사하고, 변환된 단어를 관리하여 최적의 경로를 탐색합니다.
