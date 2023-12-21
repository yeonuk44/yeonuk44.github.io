---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_The_Median
title: Finding the Median (with.Java)
# title: Finding the Median (with.Java)
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
date: 2023-12-21 09:00:00 +0900
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

## This is the "Find the median" problem.

We're going to learn by solving coding test problems, reflecting on the problems we've solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### The problem

The median is the value that is most centered when a given set of values is ordered by size.

For example, the median of 1, 2, 7, 10, and 11 is 7.

Complete the solution function so that it returns the median when given an array of integers as a parameter.

#### Example input and output

| array             | result |
| ----------------- | ------ |
| [1, 2, 7, 10, 11] | 7      |
| [9, -1, 0]        | 0      |

My solution to the ### problem

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

#### Solution

import java.util.Arrays;: imports Java's Arrays class to sort an array.

public int solution(int[] array) : Declares a function solution, it takes an integer array array as input parameter, this function returns an integer value.

int answer = 0;: Declares an integer variable, answer, to store the resulting value and initializes it to 0.

Arrays.sort(array);: Sorts the input array array. This code sorts the array in ascending order, so the smallest value in the array will be in array[0] and the largest value will be in array[array.length - 1].

answer = array[array.length / 2];: Store the element in the middle of the sorted array, the median, in the answer variable. Dividing the length of the array by 2 gives us the index of the median. This code returns exactly the median when the length of the array is odd, and the smaller of the two values in the middle when it is even.

return answer;: Returns the answer variable, including the middle value, as the return value of the function.
