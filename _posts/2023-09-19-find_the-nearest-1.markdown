---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_The_Nearest_1
title: How to find the nearest 1, output the number that meets a condition via a given index (with.Java)
# title: How to find the nearest 1, output the number that meets a condition via a given index (with.Java)

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
date: 2023-09-19 09:00:00 +0900
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

### Find the nearest 1, outputting the number fulfilling the condition through a given index (with.Java)

We're going to be solving a coding test problem, doing a retrospective on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of integers, arr. The elements of arr are either 1 or 0. Complete a solution function that, given an integer idx, finds and returns the smallest index in arr that is greater than idx and has a value of 1.

However, if there is no such index, return -1.

##### Example input and output

my_string: [0, 0, 0, 0, 1]

idx: 1

result: 3

The smallest index that is greater than 1 and has an element of 1 is 3. Therefore, it returns 3.

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
class Solution {
    public int solution(int[] arr, int idx) {
        for(int i = idx; i < arr.length; i++) {
            if(arr[i] == 1) {
                return i;
            }
        }
        return -1;
    }
}
```

##### Solution Description

This class defines a solution method that performs the following operations on a given array of integers arr and an integer idx:

Performs a loop from idx to the end of arr. IDX is the starting index, which means that it starts at this position in ARR and traverses to the end of the array.

Within the loop, we check to see if the value of arr[i] at the current index i is 1. If arr[i] is 1, return i and exit the method. This is equivalent to finding the first index above idx that has a value of 1.

If the iteration completes and no index with a value of 1 was found, return -1. This is true if, as required by the problem, there is no index in the array with a value of 1 that is greater than idx.

For example, if arr is [1, 1, 1, 1, 1, 0] and idx is 3, we would return 3 as the result because the first index with a value of 1 starting at idx is 3.
