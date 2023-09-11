---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Concatenate_Substring_To_Create_String
title: How to concatenate substring to create a string (with.Java)
# title: How to concatenate substring to create a string (with.Java)

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
date: 2023-09-10 09:00:00 +0900
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

### In this article, we learned how to concatenate partial strings to create a string (with.Java).

We've been solving coding test problems, reflecting on the problems we've solved, and learning about other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of strings of equal length my_strings and a two-dimensional integer array parts as parameters.

parts[i] is of the form [s, e], meaning the substring from index s to index e of my_string[i].

Write a solution function that returns a string of concatenated substring corresponding to parts of the elements of each my_strings.

##### Example input and output

my_string: ["progressive", "hamburger", "hammer", "ahocorasick"]

queries: [[0, 4], [1, 2], [3, 5], [7, 7]]

result: "programmers"

Solving the example, the string of each substring concatenated in order is "programmers", so it returns "programmers".

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
class Solution {
    public String solution(String[] my_strings, int[][] parts) {
        String answer = "";
        for(int i = 0; i < parts.length; i++){
            answer += my_strings[i].substring(parts[i][0], parts[i][1]+1);
        }
        } return answer;
    }
}
```

##### Solution

To implement the logic, we create a loop that traverses the length of parts, and then store the string elements of my_strings in answer of type String using the substring function.

I have inserted parts[i][0], parts[i][1]+1 in the arguments to the substring() function, which means that substring will return a string starting at startIndex and ending just before endIndex.

This is because, in simple math, startIndex <= sequence number < endIndex.

To get the return value up to index, which is what the problem requires, we need to add +1 to make it <=, so we did.
