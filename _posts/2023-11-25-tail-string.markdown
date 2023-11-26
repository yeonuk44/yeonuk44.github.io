---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Tail_String
title: Tail String (with.Java)
# title: Tail String (with.Java)
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
date: 2023-11-25 09:00:00 +0900
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

## This is a post about the "tail string" problem.

We're going to learn about it by solving coding test problems, reflecting on the problems we've solved, and exploring other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### The Problem

Given a list of strings, the string that combines all the strings in order is called the tail string.

When creating the tail string, you want to exclude strings that contain a specific string.

For example, if you have a list of strings ["abc", "def", "ghi"] and you create a tail string that excludes strings containing the string "ef", you get "abcghi".

Given a list of strings str_list and a string ex that you want to exclude, complete the solution function so that it returns a tail string created by excluding strings containing ex from str_list.

#### Example input and output

| str_list              | ex   | result   |
| --------------------- | ---- | -------- |
| ["abc", "def", "ghi"] | "ef" | "abcghi" |
| ["abc", "bbc", "cbc"] | "c"  | ""       |

My solution to the ### problem

```java
class Solution {
    public String solution(String[] str_list, String ex) {
        String answer = "";
        for(String temp: str_list){
            answer += temp.contains(ex) ? "" : temp;
        }
    } return answer;
}
```

#### solution description

String answer = "";: Initialize an empty string answer to store the result.

for(String temp : str_list) : Iterate over the array of strings str_list, examining each string temp.

answer += temp.contains(ex) ? "" : temp;: if the current string temp contains ex, add an empty string; otherwise, add the string temp to answer.

return answer;: Return answer, the result of concatenating the strings in str_list that do not contain ex.
