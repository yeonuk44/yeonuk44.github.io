---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_The_Desired_String
title: Find the desired string (with.Java)
# title:  Find the desired string (with.Java)
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
date: 2023-10-10 09:00:00 +0900
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

### In this article, we learned about finding a string.

We'll do this by solving a coding test problem, doing a retrospective on the problem we solved, and learning about other ways to solve it.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given two alphabetical strings, myString and pat.

Complete a solution function that returns 1 if pat exists in any consecutive substring of myString, and 0 otherwise.

Note that we do not distinguish between upper and lower case letters of the alphabet.

##### Example input and output

| myString  | pat     | return |
| --------- | ------- | ------ |
| "AbCdEfG" | "aBc"   | 1      |
| "aaAA"    | "aaaaa" | 0      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int solution(String myString, String pat) {
        int answer = 0;
        String lowerStr = myString.toLowerCase();
        String lowerPat = pat.toLowerCase();
        if(lowerStr.contains(lowerPat)){
            answer = 1;
        }
        } return answer;
    }
}
```

##### Solution description

int answer = 0;: Initialize the variable answer to store the result. The initial value is 0.

String lowerStr = myString.toLowerCase();: Convert the input string myString to lowercase and store it in lowerStr. The reason for doing this is to make judgments case insensitive.

String lowerPat = pat.toLowerCase();: Convert the input string pat to lowercase as well and store it in lowerPat.

if(lowerStr.contains(lowerPat)) : If the string lowerStr contains the string lowerPat:

Set answer to 1.

return answer;: Returns answer representing the result.

If lowerStr contains lowerPat, return 1; otherwise, return 0.
