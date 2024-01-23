---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Counting_Sort
title: About Counting Sort
# title: About Counting Sort
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
date: 2024-01-23 09:00:00 +0900
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

## "병합 정렬 (Merge Sort)"에 대하여

코딩테스트를 준비하며, 알고리즘에 대한 공부를 하여 이번 글에선 그 중 버블 정렬에 대해 정리하고자 합니다.

{:data-align="center"}

<!-- outline-end -->

### 병합 정렬 (Merge Sort)이란?

병합 정렬은 정렬 알고리즘 중에서 가장 유명하고 효율적인 알고리즘 중 하나로, 분할 정복(Divide and Conquer) 알고리즘의 대표적인 예입니다.

이 알고리즘은 큰 문제를 작은 문제로 분할하고, 작은 문제를 해결하여 전체 문제를 해결하는 방식으로 동작합니다.

병합 정렬은 안정적이며, 평균 시간 복잡도가 O(nlogn)으로 빠르게 동작합니다.

### 병합 정렬의 동작 과정

분할 (Divide): 배열을 두 개의 부분 배열로 분할합니다.

중간 지점을 찾고, 배열을 두 개의 하위 배열로 나눕니다.

- 정복 (Conquer): 각 하위 배열을 재귀적으로 정렬합니다. 이는 배열의 크기가 1이 될 때까지 반복됩니다.
- 병합 (Merge): 정렬된 두 하위 배열을 합병하여 최종 정렬된 배열을 생성합니다.

#### 예시

우리가 정렬할 배열은 다음과 같습니다: [38, 27, 43, 3, 9, 82, 10]

- 분할 (Divide): 배열을 중간에서 분할하면 두 개의 하위 배열이 생성됩니다.
  - 왼쪽 배열: [38, 27, 43]
  - 오른쪽 배열: [3, 9, 82, 10]
- 정복 (Conquer): 이제 각 하위 배열을 재귀적으로 정렬합니다. 하위 배열의 크기가 1이 될 때까지 계속 분할하고 정복합니다.
  - 왼쪽 배열 정렬: [27, 38, 43]
  - 오른쪽 배열 정렬: [3, 9, 10, 82]
- 병합 (Merge): 이제 정렬된 하위 배열을 병합하여 최종 정렬된 배열을 얻습니다.
  - 왼쪽 배열: [27, 38, 43]
  - 오른쪽 배열: [3, 9, 10, 82]

왼쪽과 오른쪽 배열을 순서대로 비교하면서 더 작은 값을 새 배열에 복사합니다.

이 작업을 계속하면 최종 정렬된 배열을 얻게 됩니다.

정렬된 배열: [3, 9, 10, 27, 38, 43, 82]

### 결론

병합 정렬은 효율적이고 안정적인 정렬 알고리즘으로, 대규모 데이터 집합을 정렬하는 데 사용됩니다.

이 알고리즘은 분할 정복의 아름다운 예로, 데이터를 분할하고 정복하여 정렬된 배열을 얻는 방식을 보여줍니다.

이해하기 쉬운 구조와 안정성으로, 병합 정렬은 실무에서도 널리 사용되며, 컴퓨터 과학의 기본적인 알고리즘 중 하나입니다.
