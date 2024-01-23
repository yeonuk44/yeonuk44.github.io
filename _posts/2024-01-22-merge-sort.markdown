---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Merge_Sort
title: About Merge Sort
# title: About Merge Sort
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
date: 2024-01-22 09:00:00 +0900
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

## About "Merge Sort"

In preparation for a coding test, I've been studying algorithms, and in this article, I'd like to summarize the merge sort.

{:data-align="center"}

<!-- outline-end -->

### What is Merge Sort?

Merge sort is one of the most famous and efficient sorting algorithms, and is a prime example of the Divide and Conquer algorithm.

It works by splitting a large problem into smaller problems and solving the smaller problems to solve the whole problem.

Merge Sort is stable and fast, with an average time complexity of O(nlogn).

### How Merge Sort works

Divide: Splits the array into two partial arrays.

Find the middle point, and divide the array into two subarrays.

- Conquer: Recursively sorts each sub-array. This is repeated until the size of the array is 1.
- Merge: Merges the two sorted subarrays to create a final sorted array.

#### Example

The array we want to sort is [38, 27, 43, 3, 9, 82, 10].

- Divide: Splitting the array in the middle creates two subarrays.
  - Left array: [38, 27, 43]
  - Right array: [3, 9, 82, 10].
- Conquer: Now recursively sort each subarray. Continue to divide and conquer until the size of the subarrays is 1.
  - Sort left array: [27, 38, 43]
  - Sort the right array: [3, 9, 10, 82].
- Merge: Now merge the sorted subarrays to get the final sorted array.
  - Left Array: [27, 38, 43]
  - Right array: [3, 9, 10, 82]

Compare the left and right arrays in order, copying the smaller values to the new array.

Keep doing this until you get the final sorted array.

Sorted array: [3, 9, 10, 27, 38, 43, 82]

### Conclusion

Merge sort is an efficient and reliable sorting algorithm that is used to sort large datasets.

The algorithm is a beautiful example of divide-and-conquer, showing how to divide and conquer data to get a sorted array.

Due to its easy-to-understand structure and stability, merge sort is widely used in practice and is one of the fundamental algorithms in computer science.
