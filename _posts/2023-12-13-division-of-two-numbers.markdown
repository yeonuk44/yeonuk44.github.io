---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Division_Of_Two_Numbers
title: Division of two numbers (with.Java)
# title: Division of two numbers (with.Java)
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
date: 2023-12-13 09:00:00 +0900
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

## This is a post about the "division of two numbers" problem.

We're going to solve a coding test problem, reflect on the problem we solved, and learn about other ways to solve it.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### Problem

Given the numbers num1 and num2 as parameters, complete the soltuion function so that it returns the integer part of num1 divided by num2 multiplied by 1,000.

#### Example input and output

| num1 | num2 | result |
| ---- | ---- | ------ |
| 7    | 3    | 2333   |
| 3    | 2    | 1500   |
| 1    | 6    | 62     |

My solution to the ### problem

```java
class Solution {
    public int solution(int num1, int num2) {
        int answer = 0;
        double result = ((double)num1 / num2) * 1000;
        answer = (int) result;
        return answer;
    }
}
```

#### Solution

int answer = 0;: Initialize the variable answer to store the resulting value.

(double)num1 / num2: We first cast num1 to a double, then divide by num2 to calculate the ratio of the two numbers. The reason for doing this is to get the result of the division as a real number.

- 1000: Multiplies the calculated ratio by 1000 to scale the percentage to a thousand times.

(int) result: Cast the calculated result to an integer and store it in answer.

return answer;: Returns the calculated result.
