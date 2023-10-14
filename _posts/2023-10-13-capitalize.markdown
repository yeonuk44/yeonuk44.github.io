---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Capitalize
title: Capitalize (with.Java)
# title:   Capitalize (with.Java)
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
date: 2023-10-13 09:00:00 +0900
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

### In this article, we learned how to capitalize.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given a string, myString, consisting of the alphabet.

Complete a solution function that converts all the alphabets to uppercase and returns it.

##### Example input and output

| myString  | result    |
| --------- | --------- |
| "aBcDeFg" | "ABCDEFG" |
| "AAA"     | "AAA"     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public String solution(String myString) {
        return myString.toUpperCase();
    }
}
```

##### Solution description

String solution(String myString) : Defines a function that takes a string as input.

return myString.toUpperCase();: Returns the result of converting the string myString to upper case.

This code accomplishes a simple task. It converts all the characters within the given string to uppercase and returns the result.
