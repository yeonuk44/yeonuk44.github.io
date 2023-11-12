---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_Longest_SubString
title: Find the longest substring ending in a specific string (with.Java)
# title: Find the longest substring ending in a specific string (with.Java)
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
date: 2023-11-11 09:00:00 +0900
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

### This is a recap of the "Find the longest substring ending in a specific string" problem.

We're going to look at it as a coding test problem, provide a retrospective on how we solved it, and explore other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given the strings myString and pat.

Complete a solution function that finds and returns the longest substring of myString that ends in pat.

##### Example input and output

| myString   | pat  | result     |
| ---------- | ---- | ---------- |
| "AbCdEFG"  | "dE" | "AbCdE"    |
| "AAAAaaaa" | "a"  | "AAAAaaaa" |

#### My solution to the problem

```java
class Solution {
    public String solution(String myString, String pat) {
        StringBuilder answer = new StringBuilder();
        StringBuilder answer1 = new StringBuilder();
        for(int i = 0; i < myString.length(); i++){
            answer.append(myString.charAt(i));
        }
        } int count = answer.lastIndexOf(pat);
        answer1.append(answer.substring(0,count));
        for(int j = 0; j < pat.length(); j++){
            answer1.append(pat.charAt(j));
        }
} return answer1.toString();
```

##### Solution

StringBuilder answer = new StringBuilder(); and StringBuilder answer1 = new StringBuilder();: Create two StringBuilder objects answer and answer1. These objects help us manipulate strings efficiently.

for(int i = 0; i < myString.length(); i++): Iterate over the input string myString, adding each character to answer. This ensures that answer contains the contents of myString.

int count = answer.lastIndexOf(pat);: Find the last occurrence of the string pat in the answer string and store it in count.

answer1.append(answer.substring(0, count)): Add the substring from the answer string to the last occurrence of the pat string to answer1. This substring is the string before the pat.

for(int j = 0; j < pat.length(); j++): Add each character of the pat string to answer1.

return answer1.toString();: Convert the final assembled answer1 string to a string and return it.

This code finds the last occurrence of pat in the input string myString, replaces that part of the string with pat, and returns it.
