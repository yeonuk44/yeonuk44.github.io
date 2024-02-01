---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Rock_Paper_Scissoros
title: Rock, Paper, Scissors (with.Java)
# title: Rock, Paper, Scissors (with.Java)

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
date: 2024-02-01 09:00:00 +0900
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

## This article examines the “rock, paper, scissors” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Scissors are expressed as 2, rocks are expressed as 0, and paper is expressed as 5.

When rsp, a string representing the order in which Rock, Paper, Scissors is played, is given as a parameter, complete the solution function to return a string representing the cases in which all Rock, Paper, Scissors, stored in rsp, are won.

#### Restrictions

0 < length of rsp ≤ 100

Returns a string with the same length as rsp.

rsp consists of the numbers 0, 2, and 5.

#### Input/Output Example

| rsp   | result |
| ----- | ------ |
| "2"   | "0"    |
| "205" | "052"  |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public String solution(String rsp) {
         StringBuilder answer = new StringBuilder();
         for(char ch : rsp.toCharArray()){
             if(ch == '2'){
                 answer.append('0');
             }else if(ch == '0'){
                 answer.append('5');
             }else{
                 answer.append('2');
             }
         }
         return answer.toString();
     }
}
```

### Solution explanation

Input: rsp - string to convert.

Output: converted string.

Introduction to the functions used: toCharArray(): A method that converts a string to a character array.

Use of constants: In the current code, '2', '0', and '5' are used as constants.
You can increase flexibility by replacing these constants with variables.

Input exception handling: You may need exception handling for cases where the input is null or an empty string.

Write test cases: You can verify the stability of your code by writing test cases for various inputs.
