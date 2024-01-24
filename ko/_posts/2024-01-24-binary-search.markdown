---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Binary_Search
title: 이진 탐색(Binary Search)  에 대하여
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

## "계수 정렬 (Counting Sort)"에 대하여

코딩테스트를 준비하며, 알고리즘에 대한 공부를 하여 이번 글에선 그 중 계수 정렬에 대해 정리하고자 합니다.

{:data-align="center"}

<!-- outline-end -->

### 계수 정렬 (Counting Sort)이란?

계수 정렬은 정렬 알고리즘 중에서 가장 빠른 성능을 제공하는 알고리즘 중 하나입니다.

이 알고리즘은 정수나 정수 형태로 표현 가능한 데이터에 대해 효과적으로 정렬할 수 있습니다.

계수 정렬은 다른 정렬 알고리즘과 달리 비교를 하지 않는 선형 시간 복잡도를 가지며, 입력 데이터의 범위가 제한된 경우에 빛을 발합니다.

### 계수 정렬의 동작 과정

- 카운팅 (Counting): 입력 배열의 각 요소를 세어서 각 요소의 빈도를 기록한 카운트 배열을 생성합니다.
- 누적 카운트 (Cumulative Count): 각 카운트 배열의 원소를 현재 원소와 이전 원소의 합으로 업데이트합니다. 이 단계는 정렬된 배열의 각 원소가 어느 위치에 배치될지를 결정합니다.
- 정렬 (Sorting): 입력 배열을 순회하면서, 각 원소를 그 원소의 빈도를 통해 정렬된 위치에 배치합니다. 이때, 카운트 배열을 업데이트하여 중복된 원소를 처리합니다.

#### 예시

우리가 정렬할 배열은 다음과 같습니다: [3, 5, 6, 3, 1, 1]

- 카운팅 (Counting): 입력 배열을 순회하면서 각 원소의 빈도를 세어 카운트 배열을 생성합니다.
- 카운트 배열: [0, 2, 0, 2, 0, 1, 1]
- 누적 카운트 (Cumulative Count): 누적 카운트 배열을 생성합니다.
- 누적 카운트 배열: [0, 2, 2, 4, 4, 5, 6]
- 정렬 (Sorting): 이제 원래 배열을 순회하면서 각 원소를 해당 위치에 배치합니다.
- 정렬된 배열: [1, 1, 3, 3, 5, 6]

### 결론

계수 정렬은 입력 데이터의 범위에 비례하는 성능을 제공하는 빠른 정렬 알고리즘입니다.

데이터의 범위가 작고 정수 형태로 표현 가능한 경우에 특히 유용합니다.

비교 없이도 정렬할 수 있는 특징은 다른 정렬 알고리즘과 구별되는 장점 중 하나입니다.
