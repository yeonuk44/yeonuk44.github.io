---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Shuttle_Bus_Problem
title: 2018 KAKAO BLIND RECRUITMENT problem, shuttle bus (with.Java)
# title: 2018 KAKAO BLIND RECRUITMENT problem, shuttle bus (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, queue]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-17 09:00:00 +0900
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

## 2018 KAKAO BLIND RECRUITMENT 문제, 셔틀버스 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

이중 우선순위 큐는 다음 연산을 할 수 있는 자료구조를 말합니다.

D 1 큐에서 최댓값을 삭제합니다.

D -1 큐에서 최솟값을 삭제합니다.

이중 우선순위 큐가 할 연산 operations가 매개변수로 주어질 때, 모든 연산을 처리한 후 큐가 비어있으면 [0,0] 비어있지 않으면 [최댓값, 최솟값]을 return 하도록 solution 함수를 구현해주세요.

#### 제한사항

- operations는 길이가 1 이상 1,000,000 이하인 문자열 배열입니다.
- operations의 원소는 큐가 수행할 연산을 나타냅니다.
- 원소는 “명령어 데이터” 형식으로 주어집니다.- 최댓값/최솟값을 삭제하는 연산에서 최댓값/최솟값이 둘 이상인 경우, 하나만 삭제합니다.
- 빈 큐에 데이터를 삭제하라는 연산이 주어질 경우, 해당 연산은 무시합니다.

#### 입출력 예

| operations                                                                  | return     |
| --------------------------------------------------------------------------- | ---------- |
| ["I 16", "I -5643", "D -1", "D 1", "D 1", "I 123", "D -1"]                  | [0,0]      |
| ["I -45", "I 653", "D 1", "I -642", "I 45", "I 97", "D 1", "D -1", "I 333"] | [333, -45] |

### 문제 풀이

```java
import java.util.ArrayList;
import java.util.Collections;

class Solution {
    public int[] solution(String[] operations) {
        int[] answer = {Integer.MIN_VALUE, Integer.MAX_VALUE};
        ArrayList<Integer> list = new ArrayList<>();

        for(String str : operations){
            if(str.contains("I")){
                list.add(Integer.valueOf(str.split(" ")[1]));
                Collections.sort(list);
            }
            if(str.contains("D")){
                if(list.size() == 0){continue;}
                if(str.split(" ")[1].equals("1")){
                    list.remove(list.size() - 1);
                }else{
                    list.remove(0);
                }
            }
        }


        if(list.size() == 0){
            answer[0] = 0;
            answer[1] = 0;
            return answer;
        }else{
            for(int i = 0; i < list.size(); i++){
                if(list.get(i) > answer[0]){
                    answer[0] = list.get(i);
                }
                if(list.get(i) < answer[1]){
                    answer[1] = list.get(i);
                }
            }
        }

        return answer;
    }
}
```

#### 풀이 설명

- 변수 초기화: answer 배열은 초기값으로 Integer.MIN_VALUE와 Integer.MAX_VALUE를 가집니다. list는 큐 역할을 할 ArrayList입니다.
- 명령어 처리: operations 배열의 각 문자열을 순회하며 명령어를 처리합니다. "I 숫자"가 포함된 문자열은 split을 사용하여 숫자를 추출한 후, 리스트에 추가하고 정렬합니다. "D 1"은 최댓값을, "D -1"은 최솟값을 삭제합니다.
- 결과 계산: 명령어 처리가 끝난 후, 리스트가 비어있으면 [0, 0]을 반환합니다. 비어있지 않으면 리스트를 순회하며 최댓값과 최솟값을 answer 배열에 저장합니다.

##### 결론

위와 같이 이중 우선순위 큐를 구현할 수 있습니다.

이 방법은 명령어를 순서대로 처리하고, ArrayList를 사용하여 간단히 구현할 수 있는 장점이 있습니다.

큐의 상태에 따라 명령어를 적절히 처리하여 최종 결과를 도출하는 방식입니다.
