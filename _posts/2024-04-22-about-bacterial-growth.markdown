---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Bacterial_Growth
title: Bacterial growth (with.Java)
# title: Bacterial growth (with.Java)
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
date: 2024-04-22 09:00:00 +0900
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

## This article looks into the problem of “bacterial proliferation (with.Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

It is said that some bacteria multiply twice in one hour.

When the initial number of bacteria n and the elapsed time t are given as parameters, complete the solution function so that it returns the number of bacteria after t time.

#### Restrictions

- 1 ≤ n ≤ 10
- 1 ≤ t ≤ 15

#### Input/Output Example

<!-- | n | result |
| --- | ------ |
| 144 | 1 |
| 976 | 2 | -->

| n   | t   | result |
| --- | --- | ------ |
| 2   | 10  | 2048   |
| 7   | 15  | 229376 |

### My solution to the problem

```java
class Solution {
     public int solution(int n, int t) {
         int answer = n;
         for(int i = 0; i < t; i++){
             answer *= 2;
         }
         return answer;
     }
}
```

### Solution explanation

int answer = n;: Initializes the answer variable to n.

for(int i = 0; i < t; i++): Executes a loop that repeats from 0 to t-1.

Multiply the answer by 2.

return answer;: Finally returns the answer value.

This code has a function that repeats n t times and returns the value multiplied by 2.

For example, if n is 2 and t is 3, repeat 2 3 times and return 8.
