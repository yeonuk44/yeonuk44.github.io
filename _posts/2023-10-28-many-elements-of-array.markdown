---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Many_Elements_Of_Array
title: Add as many elements of an array (with.Java)
# title: Add as many elements of an array (with.Java)
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
date: 2023-10-28 09:00:00 +0900
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

### In this article, we learned how to add as many elements as an array.

We're going to solve a coding test problem, provide a retrospective on the problem we solved, and learn about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You have an empty array X that doesn't contain any elements.

Write a solution function that, given an array arr of positive integers as a parameter, iterates over the elements in arr, starting at the front of arr, and if an element is a, adds a to the end of X a number of times, and then returns the array X after iterating over the elements.

##### Example input and output

| arr       | result                                           |
| --------- | ------------------------------------------------ |
| [5, 1, 4] | [5, 5, 5, 5, 5, 5, 1, 4, 4, 4, 4]                |
| [6, 6]    | [6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6] |
| [1]       | [1]                                              |

#### My solution to the problem

```java
class Solution {
    public int[] solution(int[] arr) {
        int length = 0;
        for(int i = 0; i < arr.length; i++){
            length += arr[i];
        }
        int[] answer = new int[length];
        int idx = 0;
        for(int i = 0; i < arr.length; i++){
            for(int j = 0; j < arr[i]; j++){
                answer[idx++] = arr[i];
            }
        }
    } return answer;
}
```

##### Solution

The given code is a function that creates and returns a new array answer by duplicating each element in the integer array arr given as input by the value of that element. Let's briefly describe the code

int length = 0;: Initialize the variable length to determine the length of the new array answer.

First iteration (for(int i = 0; i < arr.length; i++)): Iterates over the input array arr, adding the value of each element and storing it in the length variable. This determines the total length of the answer array.

int[] answer = new int[length];: Create a new integer array answer with a length based on the length variable.

int idx = 0;: Initialize the variable idx, which keeps track of the index at which to assign a value to the answer array.

The second iteration (for(int j = 0; j < arr[i]; j++) inside for(int i = 0; i < arr.length; i++)): iterates over the array arr again, iterating over each element's value (arr[i]) and duplicating that element into the array answer.

This ensures that if an element has a value of 2, that element appears twice in the answer array.

return answer;: Returns the finalized answer array.
