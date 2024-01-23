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

## About "Counting Sort"

In preparation for a coding test, I've been studying algorithms, and in this article, I'd like to summarize the counting sort.

{:data-align="center"}

<!-- outline-end -->

### What is Counting Sort?

Counting sort is one of the fastest performing sorting algorithms.

It can effectively sort on data that can be represented as integers or whole numbers.

Unlike other sorting algorithms, Counting Sort has linear time complexity with no comparisons, and it shines when the range of input data is limited.

### How does counting sort work?

- Counting: Counts each element of the input array, creating a count array that records the frequency of each element.
- Cumulative Count: Updates the elements in each count array with the sum of the current element and the previous element. This step determines where each element will be placed in the sorted array.
- Sorting: Traverses the input array, placing each element in a position sorted by the frequency of that element. It handles duplicate elements by updating the counts array.

#### Example

The array we want to sort is [3, 5, 6, 3, 1, 1].

- Counting: Creates a count array by traversing the input array and counting the frequency of each element.
- Count array: [0, 2, 0, 2, 0, 1, 1, 1]
- Cumulative Count: Generates a cumulative count array.
- Cumulative count array: [0, 2, 2, 4, 4, 4, 5, 6].
- Sorting: Now traverses the original array, placing each element at its position.
- Sorted array: [1, 1, 3, 3, 5, 6]

### Conclusion

Counting sort is a fast sorting algorithm that provides performance that is proportional to the range of the input data.

It is especially useful when the range of the data is small and can be represented as an integer.

Its ability to sort without comparison is one of the things that distinguishes it from other sorting algorithms.
