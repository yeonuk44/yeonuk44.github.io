---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Create_An_Array_1
title: Create an array1 (with.Java)
# title: Create an array1 (with.Java)

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
date: 2023-09-15 09:00:00 +0900
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

### Create an array1(with.Java)

We're going to solve a coding test problem, and we're going to do a retrospective on the problem we solved, as well as learn about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given integers n and k, complete a solution function that returns an array that stores multiples of k in ascending order among the integers n > 1 and n < 1.

##### Example input and output

| n | k | result |
| --- | --- | | ----------- |
| 10 | 3 | [3, 6, 9] |
| 15 | 5 | [5, 10, 15] |

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
class Solution {
    public int[] solution(int n, int k) {
        int[] answer = new int[n/k];
        int j = 0;
        for(int i = 1; i <= n; i++){
            if(i % k == 0) answer[j++] = i;
        }
        } return answer;
    }
}
```

##### solution

int[] answer = new int[n/k];: Create an integer array answer of length n/k. This array will be used to store numbers that are multiples of k.

int j = 0;: Initialize the index variable j for storing numbers in the array answer.

for(int i = 1; i <= n; i++) {: Iterate over the numbers from 1 to n, examining them.

if(i % k == 0) answer[j++] = i;: Check if the current number i is a multiple of k. If i is a multiple of k, store its value in the array answer and increment j, ready to store it at the next index.

return answer;: Returns the array answer, which finally holds the number that is a multiple of k.

This code performs the simple task of finding multiples of k within a given range and storing them in an array. The returned array stores the multiples of k in ascending order.
