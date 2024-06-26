---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Binary_Search
title: 이진 탐색(Binary Search) 에 대하여
# title: About Binary Search
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Algorithm
# multiple tag entries are possible
tags: [algorithm]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-24 09:00:00 +0900
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

## "이진 탐색(Binary Search)"에 대하여

이진 탐색(Binary Search) 알고리즘은 컴퓨터 과학과 알고리즘 이론에서 가장 중요하면서 효율적인 탐색 알고리즘 중 하나입니다.

이 알고리즘은 데이터 집합 내에서 특정한 값을 찾거나, 조건을 만족하는 원소를 효율적으로 찾을 때 사용됩니다.

이 글에서는 이진 탐색의 개념, 작동 방식, 구현, 그리고 실제 상황에서의 활용에 대해 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 이진 탐색(Binary Search)이란?

이진 탐색은 정렬된 데이터 집합 내에서 원하는 값을 찾는 알고리즘입니다.

이 알고리즘은 데이터를 반으로 나누어 검색 범위를 절반으로 줄여가면서 원하는 값을 찾는 방식으로 동작합니다.

이러한 반복적인 과정을 통해 매우 빠르게 원하는 값을 찾을 수 있습니다.

### 이진 탐색의 작동 방식

- 가운데 원소를 선택합니다.
- 선택한 원소와 찾고자 하는 값을 비교합니다.
- 만약 선택한 원소가 찾고자 하는 값과 동일하다면, 검색이 종료됩니다.
- 만약 선택한 원소가 찾고자 하는 값보다 크다면, 오른쪽 반쪽만 남기고 다시 검색합니다.
- 만약 선택한 원소가 찾고자 하는 값보다 작다면, 왼쪽 반쪽만 남기고 다시 검색합니다.

위 과정을 반복하여 원하는 값을 찾을 때까지 계속합니다.

### 이진 탐색의 구현

이진 탐색은 재귀 또는 반복문을 통해 구현할 수 있습니다.

아래는 반복문을 사용한 이진 탐색의 간단한 구현입니다.

```java
int binarySearch(int arr[], int target) {
    int left = 0, right = arr.length - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;

        if (arr[mid] == target)
            return mid;

        if (arr[mid] < target)
            left = mid + 1;
        else
            right = mid - 1;
    }

    return -1; // 찾지 못한 경우
}

```

### 이진 탐색의 활용

이진 탐색은 배열 내에서 특정 값의 존재 여부를 확인하거나, 원하는 값을 빠르게 찾을 때 사용됩니다.

예를 들어, 정렬된 목록에서 항목을 찾거나, 특정 범위 내에서 값의 존재 여부를 확인하는 데 매우 유용합니다.

이진 탐색은 데이터베이스 쿼리 최적화, 게임 프로그래밍, 검색 엔진 및 정렬 알고리즘에서 활발하게 사용됩니다.

### 결론

이진 탐색은 정렬된 데이터 집합에서 원하는 값을 빠르게 찾는 효율적인 알고리즘입니다.

이 알고리즘을 이해하고 활용하면 데이터 검색과 관련된 많은 문제를 더 효과적으로 해결할 수 있습니다.
