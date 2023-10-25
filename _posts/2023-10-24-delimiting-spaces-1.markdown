---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Delimiting_Spaces_1
title: Delimiting Spaces 1 (with.Java)
# title: Delimiting Spaces 1 (with.Java)
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
date: 2023-10-24 09:00:00 +0900
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

### This is the first installment of our series on Space Separator 1.

We're going to be solving coding test problems, reflecting on the problems we've solved, and learning about other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given a string my_string with words separated by a single space as a parameter, write a solution function that returns an array of strings containing the words in my_string, ordered from front to back.

##### Example input and output

| my_string     | result               |
| ------------- | -------------------- |
| "i love you"  | ["i", "love", "you"] |
| "programmers" | ["programmers"]      |

#### My solution to the problem

```java
class Solution {
    public String[] solution(String my_string) {
        String[] answer = my_string.split(" ");
        return answer;
    }
}
```

##### Solution Explained

Solved by using the SPLIT function to sequentially store spaces as separators in an array of strings to match the conditions of the problem.
