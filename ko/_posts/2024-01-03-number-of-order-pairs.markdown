---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Of_Order_Pairs
title: 순서쌍의 개수(with.Java)
# title: Number of order pairs (with.Java)
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
date: 2024-01-03 09:00:00 +0900
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

## "진료 순서 정하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

외과의사 머쓱이는 응급실에 온 환자의 응급도를 기준으로 진료 순서를 정하려고 합니다.

정수 배열 emergency가 매개변수로 주어질 때 응급도가 높은 순서대로 진료 순서를 정한 배열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

중복된 원소는 없습니다.

1 ≤ emergency의 길이 ≤ 10

1 ≤ emergency의 원소 ≤ 100

#### 입출력 예시

| emergency             | result                |
| --------------------- | --------------------- |
| [3, 76, 24]           | [3, 1, 2]             |
| [1, 2, 3, 4, 5, 6, 7] | [7, 6, 5, 4, 3, 2, 1] |
| [30, 10, 23, 6, 100]  | [2, 4, 3, 5, 1]       |

### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int[] solution(int[] emergency) {
        int[] answer = new int[emergency.length];
        Arrays.fill(answer, 1);

        for(int value : emergency){
            for(int i = 0; i < emergency.length; i++){
                if(value > emergency[i]){
                    answer[i]++;
                }
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

solution: 긴급 상황에 대한 우선순위를 계산하는 함수입니다.

입력: emergency - 긴급 상황을 나타내는 정수 배열.

출력: 긴급 상황에 대한 우선순위를 나타내는 정수 배열.

사용된 함수 소개:

Arrays.fill(answer, 1);: Arrays 클래스의 fill 메서드는 배열을 특정 값으로 채우는 데 사용됩니다.

이 경우에는 answer 배열을 1로 초기화합니다.

개선 가능한 점:

성능 개선: 현재 코드는 이중 반복문을 사용하여 각 긴급 상황에 대한 우선순위를 계산합니다.

이는 긴급 상황이 많아질수록 성능에 영향을 미칠 수 있습니다.

성능을 개선하기 위해 다른 알고리즘을 고려할 수 있습니다.

코드 모듈화: 현재 코드는 한 함수에 모두 구현되어 있습니다.

함수를 작은 단위로 나누어 코드의 모듈화를 고려할 수 있습니다.

예를 들어, 우선순위를 계산하는 부분을 별도의 함수로 분리할 수 있습니다.

자료구조 활용: 긴급 상황에 대한 우선순위를 계산하는 방식을 효율적인 자료구조로 변경하여 성능을 향상시킬 수 있습니다.

예를 들어, 힙(Heap) 자료구조를 사용하면 더 효율적인 우선순위 계산이 가능합니다.

이러한 개선점을 고려하여 코드를 더욱 효율적으로 만들 수 있습니다.
