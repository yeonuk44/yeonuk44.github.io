---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Alien_Language_Dictionary
title: 외계어 사전 (with.Java)
# title: Alien language dictionary (with.Java)
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
date: 2024-05-12 09:00:00 +0900
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

## "삼각형의 완성조건 2 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

선분 세 개로 삼각형을 만들기 위해서는 다음과 같은 조건을 만족해야 합니다.

가장 긴 변의 길이는 다른 두 변의 길이의 합보다 작아야 합니다.

삼각형의 두 변의 길이가 담긴 배열 sides이 매개변수로 주어집니다.

나머지 한 변이 될 수 있는 정수의 개수를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- sides의 원소는 자연수입니다.
- sides의 길이는 2입니다.
- 1 ≤ sides의 원소 ≤ 1,000

#### 입출력 예시

<!-- | keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] | -->

| sides   | result |
| ------- | ------ |
| [1, 2]  | 1      |
| [3, 6]  | 5      |
| [11, 7] | 13     |

### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int solution(int[] sides) {
        int answer = 0;
        Arrays.sort(sides);

        for(int i = (sides[1] - sides[0]) + 1; i <= sides[1]; i++){
            answer++;
        }
        for(int i = sides[1] + 1; i < sides[0] + sides[1]; i++){
            answer++;
        }

        return answer;
    }
}

```

### 풀이 설명

주어진 배열을 오름차순으로 정렬합니다.

이렇게 함으로써 배열의 첫 번째 원소는 가장 작은 값이 되고, 두 번째 원소는 더 큰 값이 됩니다.

첫 번째 for 루프에서는 두 번째 원소와 첫 번째 원소의 차이에 1을 더한 값부터 두 번째 원소까지 반복하며 answer 값을 증가시킵니다.

이는 두 번째 원소와 첫 번째 원소 사이의 모든 값을 포함하기 위한 것입니다.

예를 들어, 만약 sides 배열이 [3, 7]으로 주어진다면, 첫 번째 for 루프에서는 4부터 7까지 반복하며 answer 값을 4번 증가시킵니다.

두 번째 for 루프에서는 두 번째 원소보다 큰 값부터 첫 번째 원소와 두 번째 원소의 합보다 작은 값까지 반복하며 answer 값을 증가시킵니다.

이는 두 번째 원소보다 크고 첫 번째 원소와 두 번째 원소의 합보다 작은 모든 값을 포함하기 위한 것입니다. 예를 들어, 만약 sides 배열이 [3, 7]으로 주어진다면, 두 번째 for 루프에서는 8부터 9까지 반복하며 answer 값을 2번 증가시킵니다.

최종적으로 계산된 answer 값을 반환합니다.

이 코드의 장단점은 다음과 같습니다:

- 장점: 코드가 간결하고 직관적입니다. 주어진 배열에서 특정한 규칙에 따라 answer 값을 계산하는 것이 목적이므로, 간단한 반복문과 조건문을 사용하여 구현되었습니다. 배열을 정렬한 후에 계산을 수행하기 때문에, 정렬된 배열을 사용하는 다른 계산에도 유용하게 활용될 수 있습니다.
- 단점: 주어진 코드에서는 주어진 규칙에 대한 설명이 없기 때문에, 코드만으로는 어떤 규칙을 따르는지 이해하기 어렵습니다. 따라서 추가적인 정보가 필요합니다. 코드에서 사용된 변수명이 명확하지 않아 가독성이 떨어질 수 있습니다. 변수명을 좀 더 의미있게 지정하면 코드의 이해가 쉬워질 수 있습니다.
