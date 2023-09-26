---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Starting_With_The_n_th_Element
title: Starting with the n th element (with.Java)
# title: Starting with the n th element (with.Java)

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
date: 2023-09-26 09:00:00 +0900
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

### Starting with the nth element, we learned how to return a new list from a list of integers, starting with the nth element and ending with the last element.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given an integer list num_list and an integer n, complete the solution function so that it returns a list containing all elements from the nth to the last element.

##### Example input and output

num_list: [2, 1, 6]

n: 3

result: [6]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = new int[num_list.length - n + 1];
        for(int i = n - 1; i < num_list.length; i++){
            answer[i - n + 1] = num_list[i];
        }
        } return answer;
    }
}
```

##### Solution Description

The solution method inside the Solution class takes two parameters.

The first parameter is an array of integers called num_list, and the second parameter is an integer called n.

Define the size of the array: Size a new array named answer by calculating the length from the nth to the last element of num_list.

The size of the array will be num_list.length - n + 1.

Copy through a loop: Use a for loop to copy the values in num_list from the nth element to the last element into the answer array.

The i variable starts at n - 1 and iterates until it is less than num_list.length, which allows us to handle zero-based indexing in Java.

Return the result: When the copying is complete, we return the answer array. This array contains the values from the nth to the last element of num_list.
