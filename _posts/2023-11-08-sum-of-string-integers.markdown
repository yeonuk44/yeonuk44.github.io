---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sum_Of_String_Integers
title: Sum of String Integers (with.Java)
# title: Sum of String Integers (with.Java)
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
date: 2023-11-08 09:00:00 +0900
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

### This is the "sum of string integers" problem.

We're going to learn about it by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

#### Problem

Complete the solution function so that, given a string num_str of single-digit integers, it returns the sum of each digit.

##### Example input and output

| num_str     | result |
| ----------- | ------ |
| "123456789" | 45     |
| "1000000"   | 1      |

#### My solution to the problem

```java
class Solution {
    public int solution(String num_str) {
        int answer = 0;
        for(int i = 0; i < num_str.length(); i++){
            answer += Integer.parseInt(String.valueOf(num_str.charAt(i)));
        }
    } return answer;
}
```

##### solution description

int answer = 0;: Initialize the variable answer to store the result. The initial value is 0.

for(int i = 0; i < num_str.length(); i++): Iterate over the input string num_str, checking each character.

num_str.charAt(i): Get the character located at the current index i.

String.valueOf(...): Converts a character to a string.

Integer.parseInt(...): Converts a string to an integer. Add the converted value to answer.

return answer;: Returns the result of adding all the numbers contained in the string.

This code adds all the numbers in the input string and returns the sum.

It iterates through the string character by character, converting each character to an integer, adding them together, and finally returning the sum of the additions.
