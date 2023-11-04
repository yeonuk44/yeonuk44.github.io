---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Bubble_Sort
title: Comparing Arrays (with.Java)
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

### This article introduces bubble sorting.

In preparation for a coding test, I've been studying algorithms, and in this article, I'd like to summarize the bubble sort.

{:data-align="center"}

<!-- outline-end -->

#### What is bubble sort?

Bubble sorting is an algorithm that compares two adjacent elements, shifting smaller values to the left.

#### Understanding Bubble Sort

Initial array: [5, 2, 9, 1, 5, 6]

First pass: [2, 5, 1, 5, 6, 9].

- Compare and swap the first and second elements. The 5 is exchanged for the 2.
- Next, compare and exchange the second and third elements. The 5 is exchanged for the 9.
- This process continues until the largest element is moved to the far right.
- At the end of this pass, the largest element is aligned to the far right.

Second pass: [2, 1, 5, 5, 6, 9].

- Again, starting with the first, the first and second elements are compared and swapped. This time, the 2 and 5 are not exchanged.
- Compare and exchange the second and third elements. The 5 and 1 are exchanged.
- This process is repeated until the second largest element is sorted in front of the one from the far right.

Final sorted array: [1, 2, 5, 5, 6, 9].

- Repeat the above process, performing passes the length of the array.
- In each pass, the largest value is moved to the far right, so the unaligned portion decreases as the passes progress.

##### See

This is how bubble sorting works, starting with the largest value in the array and moving it to the right in turn. The efficiency of this algorithm is poor, so it's not recommended for large arrays.
