---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_An_Integer
title: Find an integer (with.Java)
# title: Find an integer (with.Java)
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
date: 2023-11-26 09:00:00 +0900
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

## This is the "Find an integer" problem.

We're going to learn about it by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

Given a list of integers num_list and an integer n to be found, complete the solution function so that it returns 1 if n is in num_list and 0 otherwise.

#### Example input and output

| num_list            | n   | result |
| ------------------- | --- | ------ |
| [1, 2, 3, 4, 5]     | 3   | 1      |
| [15, 98, 23, 2, 15] | 20  | 0      |

My solution to the ### problem

```java
class Solution {
    public int solution(int[] num_list, int n) {
        int answer = 0;
        for(int temp: num_list){
            if(temp == n){
                answer = 1;
            }
        }
    } return answer;
}
```

#### solution description

int answer = 0;: Initialize an integer variable, answer, to store the result. The initial value is 0.

for(int temp : num_list) : Iterates over the integer array num_list, examining each element temp.

if(temp == n) : If the current element temp is equal to n received as input:

Set answer to 1.

return answer; : Returns the value of answer representing the result of the judgment.
