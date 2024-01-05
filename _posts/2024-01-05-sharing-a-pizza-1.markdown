---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sharing_A_Pizza_1
title: Sharing a Pizza 1 (with.Java)
# title: Sharing a Pizza 1 (with.Java)
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
date: 2024-01-05 09:00:00 +0900
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

## This is a recap of the "Share a Pizza 1" problem.

We're going to learn by solving coding test problems, reflecting on the problems we've solved, and exploring other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### Problem

A pizza parlor cuts a pizza into seven slices.

Given the number of people to share the pizza, n, complete a solution function that returns the number of slices needed to ensure that everyone gets at least one slice.

#### Example input and output

| n   | result |
| --- | ------ |
| 7   | 1      |
| 1   | 1      |
| 15  | 3      |

My solution to the ### problem

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        if(n % 7 == 0){
            answer = n / 7;
        }else{
            answer = n / 7 + 1;
        }
        return answer;
    }
}
```

#### Solution Description

public int solution(int n) : Declares a function solution, which takes a positive integer n as an input parameter. The function returns an integer value.

int answer = 0;: Declares the integer variable answer and initializes it to 0. This variable will store the result.

if (n % 7 == 0): If the input integer n is divided by 7 and the remainder is 0, that is, if n is a multiple of 7, perform the following operation.

answer = n / 7;: store the quotient of n divided by 7 in the variable answer. This way, if it is a multiple of 7, the quotient represents the exact value.

else: If it is not a multiple of 7, that is, if n is not a multiple of 7, do the following

answer = n / 7 + 1;: Store the quotient of n divided by 7 plus 1 in the answer variable. This will represent the remainder, if any, rounded up to the next integer.

return answer;: Returns the final result, the value answer, as the return value of the function.
