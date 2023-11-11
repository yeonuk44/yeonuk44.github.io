---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Convert_String_To_Integer
title: Convert a string to an integer (with.Java)
# title: Convert a string to an integer (with.Java)
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
date: 2023-11-10 09:00:00 +0900
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

### This is a recap of the "Convert a string to an integer" problem.

We're going to learn by solving coding test questions, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Complete the solution function so that, given a string n_str consisting of only numbers, it converts n_str to an integer and returns it.

##### Example input and output

| n_str  | result |
| ------ | ------ |
| "10"   | 10     |
| "8542" | 8542   |

#### My solution to the problem

```java
class Solution {
    public int solution(String n_str) {
        int answer = Integer.parseInt(n_str);
        return answer;
    }
}
```

##### Explanation of the solution

The Integer.parseInt() function was used to return a string as an integer.
