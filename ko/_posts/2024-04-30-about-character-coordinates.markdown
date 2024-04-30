---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Character_Coordinates
title: 최댓값 만들기 2 (with.Java)
# title: Creating maximum value 2 (with.Java)
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
date: 2024-04-30 09:00:00 +0900
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

## "최댓값 만들기 2 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 배열 numbers가 매개변수로 주어집니다.

numbers의 원소 중 두 개를 곱해 만들 수 있는 최댓값을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- -10,000 ≤ numbers의 원소 ≤ 10,000
- 2 ≤ numbers 의 길이 ≤ 100

#### 입출력 예시

<!-- | keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] | -->

| numbers                   | result |
| ------------------------- | ------ |
| [1, 2, -3, 4, -5]         | 15     |
| [0, -31, 24, 10, 1, 9]    | 240    |
| [10, 20, 30, 5, 5, 20, 5] | 600    |

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public int solution(int[] numbers) {
        Arrays.sort(numbers);

        int n = numbers.length;
        int maxNegative = numbers[0] * numbers[1];
        int maxPositive = numbers[n - 1] * numbers[n - 2];

        return Math.max(maxNegative, maxPositive);
    }
}

```

### 풀이 설명

- 배열 정렬: 주어진 배열을 정렬하여 음수와 양수를 구분합니다.
- 음수 중 가장 큰 두 수 선택: 정렬된 배열의 첫 번째와 두 번째 요소를 선택하여 음수 중 가장 큰 두 수를 곱한 값을 계산합니다.
- 양수 중 가장 큰 두 수 선택: 정렬된 배열의 마지막과 마지막에서 두 번째 요소를 선택하여 양수 중 가장 큰 두 수를 곱한 값을 계산합니다.
- 결과 반환: 음수와 양수를 곱한 값 중 더 큰 값을 반환합니다.

**코드 장점**

- 간단한 로직: 배열을 정렬하고 가장 큰 수와 두 번째로 큰 수를 선택하여 곱하는 간단한 방법을 사용했습니다.
- 정렬을 통한 효율성: 정렬된 배열을 사용하여 가장 큰 수를 선택하는 과정을 빠르고 간단하게 구현했습니다.

**코드 단점**

- 배열 정렬로 인한 시간 복잡도: 배열을 정렬하는 과정에 대한 시간 복잡도가 O(n log n)으로, 배열이 큰 경우 성능에 영향을 줄 수 있습니다.
