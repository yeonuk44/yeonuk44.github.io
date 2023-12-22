---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Array_Truncation
title: Array Truncation (with.Java)
# title: Array Truncation (with.Java)
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
date: 2023-12-22 09:00:00 +0900
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

## "중앙값 구하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

중앙값은 어떤 주어진 값들을 크기의 순서대로 정렬했을 때 가장 중앙에 위치하는 값을 의미합니다.

예를 들어 1, 2, 7, 10, 11의 중앙값은 7입니다.

정수 배열 array가 매개변수로 주어질 때, 중앙값을 return 하도록 solution 함수를 완성해보세요.

#### 입출력 예시

| array             | result |
| ----------------- | ------ |
| [1, 2, 7, 10, 11] | 7      |
| [9, -1, 0]        | 0      |

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;
class Solution {
    public int solution(int[] array) {
        int answer = 0;
        Arrays.sort(array);
        answer = array[array.length / 2];
        return answer;
    }
}
```

#### 풀이 설명

import java.util.Arrays;: 배열을 정렬하기 위해 Java의 Arrays 클래스를 임포트합니다.

public int solution(int[] array) : 함수 solution을 선언하고, 정수 배열 array를 입력 매개변수로 받습니다. 이 함수는 정수 값을 반환합니다.

int answer = 0;: 결과 값을 저장할 정수형 변수 answer를 선언하고 0으로 초기화합니다.

Arrays.sort(array);: 입력된 배열 array를 정렬합니다. 이 코드는 배열을 오름차순으로 정렬합니다. 따라서 배열의 가장 작은 값은 array[0]에, 가장 큰 값은 array[array.length - 1]에 위치하게 됩니다.

answer = array[array.length / 2];: 정렬된 배열에서 중간에 위치한 요소, 즉 중간값(median)을 answer 변수에 저장합니다. 배열의 길이를 2로 나누면 중간값의 인덱스가 됩니다. 이 코드는 배열의 길이가 홀수일 때는 정확히 중간값을, 짝수일 때는 중간에 있는 두 값 중 작은 값을 반환합니다.

return answer;: 중간값을 포함한 answer 변수를 함수의 반환 값으로 반환합니다.
