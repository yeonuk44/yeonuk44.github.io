---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Vowel_Dictionary
title: 모음 사전 (with.Java)
# title: Vowel dictionary (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-12 09:00:00 +0900
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

## 모음 사전 (with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

사전에 알파벳 모음 'A', 'E', 'I', 'O', 'U'만을 사용하여 만들 수 있는, 길이 5 이하의 모든 단어가 수록되어 있습니다.

사전에서 첫 번째 단어는 "A"이고, 그다음은 "AA"이며, 마지막 단어는 "UUUUU"입니다.

단어 하나 word가 매개변수로 주어질 때, 이 단어가 사전에서 몇 번째 단어인지 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- word의 길이는 1 이상 5 이하입니다.
- word는 알파벳 대문자 'A', 'E', 'I', 'O', 'U'로만 이루어져 있습니다.

#### 입출력 예시

| word    | result |
| ------- | ------ |
| "AAAAE" | 6      |
| "AAAE"  | 10     |
| "I"     | 1563   |
| "EIO"   | 1189   |

### 문제에 대한 나의 풀이

```java
import java.util.ArrayList;

class Solution {
    static ArrayList<String> list;
    static String[] words = {"A", "E", "I", "O", "U"};

    public int solution(String word) {
        int answer = 0;
        list = new ArrayList<>();

        dfs("", 0);
        int size = list.size();

        for (int i = 0; i < size; i++) {
            if (list.get(i).equals(word)) {
                answer = i;
                break;
            }
        }

        return answer;
    }

    static void dfs(String str, int len) {
        list.add(str);
        if (len == 5) return;

        for (int i = 0; i < 5; i++) {
            dfs(str + words[i], len + 1);
        }
    }
}
```

### 풀이 설명

- word: 찾고자 하는 문자열
- answer: 결과값을 저장하는 변수
- 단어들의 모든 조합을 생성한 후, 주어진 문자열이 몇 번째로 나오는지 확인하여 반환합니다.
- DFS 탐색을 통한 단어 생성
- dfs 메서드를 통해 단어의 모든 조합을 생성합니다.
- 현재 문자열 str에 각각의 모음을 추가하여 다음 레벨의 문자열을 생성합니다.
- DFS 탐색을 통해 모든 조합을 생성하고, 이를 list에 저장합니다.
- 주어진 문자열이 몇 번째로 나오는지 확인
- 생성된 모든 조합을 확인하여 주어진 문자열과 일치하는 경우 해당 인덱스를 반환합니다.

### 결론

이렇게 코드는 DFS 탐색을 통해 주어진 모음으로 구성된 단어들의 모든 조합을 생성하고, 주어진 문자열이 몇 번째로 나오는지를 찾습니다.
