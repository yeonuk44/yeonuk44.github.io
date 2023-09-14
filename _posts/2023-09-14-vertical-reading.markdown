---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Vertical_Reading
title: About Vertical Reading (with.Java)
# title: About Vertical Reading (with.Java)

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
date: 2023-09-14 09:00:00 +0900
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

### This is an article about how to read vertically (with.Java).

We've been solving coding test problems, reflecting on the problems we've solved, and learning about other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given a string my_string and two integers m, c.

Write a solution function that returns as a string the characters written in the cth column from the left when my_string is written horizontally with m characters per line.

##### Example input and output

my_string: "ihrhbakrfpndopljhygc"

m: 4

c: 2

result: "happy"

If you write my_string with 4 characters per line, the table looks like this

| Column 1 | Column 2 | Column 3 | Column 4 |
| --- | --- | --- | --- | --- | |
| i | h | r | h |
| b | a | k | r |
| f | p | n | d |
| o | p | l | j |
| h | y | g | c |

Return "happy" because the letter in column 2 reads happy when read vertically.

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
class Solution {
    public String solution(String my_string, int m, int c) {
        char[] arr = my_string.toCharArray();
        char[] arr1 = new char[arr.length/m];
        int j = 0;
        for(int i = c-1; i < arr.length; i+=m){
            arr1[j++] = arr[i];
        }
        } return new String(arr1);
    }
}
```

##### Solution Explained

To establish the matrix, we first need to convert the string type to Char type and store it as an array.

To do so, we store my_string in an array of type char[] with toCharArray().

After that, we need to make arr1 of the same type to store the return value, and the size of the array is how many columns from the length of arr.

So, I declared a divide-and-conquer loop to set the conditions the way the problem requires, and stored and returned the element with the specific IDX from the matrix.
