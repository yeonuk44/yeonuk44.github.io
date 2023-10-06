---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Add_Until_n_Greater_Than
title: Add until n is greater than (with.Java)
# title: Add until n is greater than (with.Java)

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
date: 2023-10-05 09:00:00 +0900
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

### In this article, we learned how to add until n is greater than n (with.Java).

We'll do this by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

An array of integers numbers and an integer n are given as parameters.

Write a solution function that adds the elements of numbers one by one, starting at the front, and returns the sum of the elements added up to this point when the sum is greater than n.

##### Example input and output

| numbers                  | n   | result |
| ------------------------ | --- | ------ |
| [34, 5, 71, 29, 100, 34] | 123 | 139    |
| [58, 44, 27, 10, 100]    | 139 | 239    |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int solution(int[] numbers, int n) {
        int answer = 0;
        for(int i = 0; i < numbers.length; i++){
            answer += numbers[i];
            if(answer > n) break;
        }
        } return answer;
    }
}
```

##### solution description

int answer = 0; : Initialize the variable answer to store the result.

for(int i = 0; i < numbers.length; i++) : Iterate over the input array numbers, examining each element.

answer += numbers[i];: add the current element to answer. This will sequentially sum the elements of the array.

if(answer > n) break;: Terminates the loop if the sum exceeds n. In other words, stops summing the moment the sum exceeds n.

return answer;: Returns the final summed result, answer.
