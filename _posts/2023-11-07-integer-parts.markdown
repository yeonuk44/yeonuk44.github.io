---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Integer_Parts
title: Integer parts (with.Java)
# title: Integer parts (with.Java)
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
date: 2023-11-07 09:00:00 +0900
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

### This is a post about the "integer partials" problem.

We're going to learn about it by solving coding test problems, reflecting on the problems we've solved, and exploring other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

#### Problem

Complete the solution function so that, given a real number flo as a parameter, it returns the integer part of flo.

##### Example input and output

| flo   | result |
| ----- | ------ |
| 1.42  | 1      |
| 69.32 | 69     |

#### My solution to the problem

```java
class Solution {
    public int solution(double flo) {
        int answer = (int) flo;
        return answer;
    }
}
```

##### Solution Explained

To convert a float value to an int value, you must use explicit casting.

When converting from a float value to an int value, decimal values are discarded. In Java, we use (int) to perform the cast.

See ######

Casting can cause data loss, so you should be careful. If you want to preserve decimal values, you should use rounding or other methods.
