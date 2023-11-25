---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Check_Substring
title: Check if it's a substring (with.Java)
# title: Check if it's a substring (with.Java)
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
date: 2023-11-24 09:00:00 +0900
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

## This is the "Check if it's a substring" problem.

We're going to go through the process of solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### The problem

A substring is a string that corresponds to a contiguous portion of a string.

For example, the strings "ana", "ban", "anana", "banana", and "n" are all substrings of the string "banana", but "aaa", "bnana", and "wxyz" are not all substrings of "banana".

Given the strings my_string and target as parameters, write a solution function that returns 1 if target is a substring of the string my_string and 0 otherwise.

#### Example input and output

| my_string | target | result |
| --------- | ------ | ------ |
| "banana"  | "ana"  | 1      |
| "banana"  | "wxyz" | 0      |

My solution to the ### problem

```java
class Solution {
    public int solution(String my_string, String target) {
        int answer = 0;
        if(my_string.contains(target)){
            answer = 1;
        }
    } return answer;
}
```

#### Solution Explanation

The contains method, which checks whether a string contains a target, is built into Java's String class.

If my_string contains target as a substring, the character was solved by assigning 1 to answer.

See ####

The contains method is case sensitive, so you need to be careful.

If you want to ignore case and check for inclusion, you can do so after converting the string to all lowercase or all uppercase.
