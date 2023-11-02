---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Bubble_Sort
title: 버블 정렬(Bubble Sort)에 대하여
# title: Comparing Arrays (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-11-01 09:00:00 +0900
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

### 버블 정렬에 대하여 알아본 글입니다.

코딩테스트를 준비하며, 알고리즘에 대한 공부를 하여 이번 글에선 그 중 버블 정렬에 대해 정리하고자 합니다.

{:data-align="center"}

<!-- outline-end -->

#### 버블 정렬이란?

버블 정렬은 인접한 두 원소를 비교하면서 작은 값을 왼쪽으로 이동시키는 방식의 알고리즘입니다.

#### 버블 정렬의 이해

초기 배열: [5, 2, 9, 1, 5, 6]

첫 번째 패스: [2, 5, 1, 5, 6, 9]

- 첫 번째와 두 번째 원소를 비교하여 교환합니다. 5는 2와 교환됩니다.
- 다음으로 두 번째와 세 번째 원소를 비교하여 교환합니다. 5는 9와 교환됩니다.
- 이러한 과정을 계속 반복하여 가장 큰 원소가 가장 오른쪽으로 이동합니다.
- 이 패스가 끝나면 가장 큰 원소가 맨 오른쪽에 정렬됩니다.

두 번째 패스: [2, 1, 5, 5, 6, 9]

- 다시 첫 번째부터 시작하여 첫 번째와 두 번째 원소를 비교하여 교환합니다. 이때 2와 5가 교환되지 않습니다.
- 두 번째와 세 번째 원소를 비교하여 교환합니다. 5와 1이 교환됩니다.
- 이 과정을 반복하여 두 번째로 큰 원소가 맨 오른쪽에서 하나 앞에 정렬됩니다.

최종 정렬된 배열: [1, 2, 5, 5, 6, 9]

- 위의 과정을 반복하여 배열의 길이만큼 패스를 수행합니다.
- 각 패스에서 가장 큰 값이 맨 오른쪽으로 이동하므로, 패스가 진행될수록 정렬되지 않은 부분이 줄어듭니다.

##### 참고

이런식으로 버블 정렬은 배열의 가장 큰 값부터 차례대로 오른쪽으로 이동하며 정렬하는 방식입니다. 이 알고리즘의 효율성은 좋지 않아서 큰 배열에는 사용하지 않는 것이 좋습니다.
