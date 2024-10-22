---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Network
title: 네트워크 (with.Java)
# title: Network (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, dfs]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-22 09:00:00 +0900
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

## 네트워크 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

자연수 n 개로 이루어진 중복 집합(multi set, 편의상 이후에는 "집합"으로 통칭) 중에 다음 두 조건을 만족하는 집합을 최고의 집합이라고 합니다.

각 원소의 합이 S가 되는 수의 집합

위 조건을 만족하면서 각 원소의 곱 이 최대가 되는 집합

예를 들어서 자연수 2개로 이루어진 집합 중 합이 9가 되는 집합은 다음과 같이 4개가 있습니다.

{ 1, 8 }, { 2, 7 }, { 3, 6 }, { 4, 5 }

그중 각 원소의 곱이 최대인 { 4, 5 }가 최고의 집합입니다.

집합의 원소의 개수 n과 모든 원소들의 합 s가 매개변수로 주어질 때, 최고의 집합을 return 하는 solution 함수를 완성해주세요.

#### 제한사항

- 최고의 집합은 오름차순으로 정렬된 1차원 배열(list, vector) 로 return 해주세요.
- 만약 최고의 집합이 존재하지 않는 경우에 크기가 1인 1차원 배열(list, vector) 에 -1 을 채워서 return 해주세요.
- 자연수의 개수 n은 1 이상 10,000 이하의 자연수입니다.
- 모든 원소들의 합 s는 1 이상, 100,000,000 이하의 자연수입니다.

#### 입출력 예

| n   | s   | result |
| --- | --- | ------ |
| 2   | 9   | [4, 5] |
| 2   | 1   | [-1]   |
| 2   | 8   | [4, 4] |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### 문제 풀이

```java
import java.util.HashSet;
import java.util.ArrayList;
import java.util.Collections;

class Solution {
    ;
    public int[] solution(int n, int s) {
        int[] answer = new int[n];
        if(n > s){
            answer = new int[]{-1};
            return answer;
        }
        for(int i = 0; i < answer.length; i++){
            answer[i] = s / n;
        }
        int temp = s % n;
        for(int i = answer.length - 1; i >= 0; i--){
            if(temp == 0){
                break;
            }
            answer[i] += 1;
            temp--;
        }

        return answer;
    }
}
```

#### 풀이 설명

주어진 자연수 n과 s를 가지고 n개의 원소로 이루어진 배열을 만들되, 배열의 원소들의 곱이 최대가 되도록 하는 문제를 해결합니다.

이를 위해 코드에서는 다음과 같은 절차를 따릅니다.

먼저, 배열의 각 원소를 가능한 한 균등하게 나누기 위해 s를 n으로 나눈 몫을 배열 answer에 저장합니다.

이는 각 원소가 평균적으로 큰 값을 가지도록 하여 배열의 곱을 최대로 하기 위함입니다.

만약 n이 s보다 크다면, 이는 s를 n개의 원소로 나눌 수 없음을 의미하므로, -1을 원소로 가지는 배열을 반환합니다.

그 후, s를 n으로 나눈 나머지를 계산하여, 이 나머지를 배열의 뒤에서부터 1씩 더해줍니다.

이렇게 함으로써 배열의 합이 s가 되도록 조정하면서도 배열의 원소들이 가능한 한 균등하게 분포되도록 합니다.

이를 통해 배열의 곱이 최대가 되도록 합니다.

코드의 첫 번째 반복문에서는 배열 answer의 모든 원소를 s / n으로 초기화합니다.

두 번째 반복문에서는 나머지 temp 값을 이용하여 배열의 뒤에서부터 1씩 더해줍니다.

이렇게 함으로써 배열의 원소들이 가능한 한 균등하게 유지되며, 배열의 원소들의 곱이 최대가 되도록 합니다.

##### 결론

이 코드는 간단하면서도 효율적으로 문제를 해결하며, 배열의 원소들이 가능한 한 균등하게 분포되도록 함으로써 배열의 곱을 최대로 만듭니다.
