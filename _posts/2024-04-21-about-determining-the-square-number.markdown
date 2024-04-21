---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Determining_The_Square_Number
title: Determining the square number (with.Java)
# title: Determining the square number (with.Java)
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
date: 2024-04-21 09:00:00 +0900
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

## This article examines the problem of “identifying square numbers.”

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The integer that results when a natural number is squared is called a square number.

When an integer n is given as a parameter, complete the solution function so that it returns 1 if n is a square number, and 2 otherwise.

#### Restrictions

- 1 ≤ n ≤ 1,000,000

#### Input/Output Example

| n   | result |
| --- | ------ |
| 144 | 1      |
| 976 | 2      |

<!-- | str1 | str2 | result |
| ------------------------ | ------ | ------ |
| "ab6CDE443fgh22iJKlmn1o" | "6CD" | 1 |
| "ppprrogrammers" | "pppp" | 2 |
| "AbcAbcA" | "AAA" | 2 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int n) {
         int answer = 0;
         for(int i = 1; i <= 1000; i++){
             if(i * i == n){
                 answer = 1;
                 break;
             }else if(i * i > n){
                 answer = 2;
                 break;
             }
         }
         return answer;
     }
}
```

### Solution explanation

int answer = 0;: Initialize the variable answer, which will store the result, to 0.

for(int i = 1; i <= 1000; i++): This is a loop statement to sequentially check numbers from 1 to 1000.

if(i \* i == n): If the power of the current number i is equal to n, then n is a square number. So we set answer to 1 and exit the loop.

else if(i \* i > n): If the current number i squared is greater than n, then n is not a square number. So we set answer to 2 and exit the loop.

return answer;: Returns the final result answer.

This code sequentially squares numbers from 1 to 1000 and compares them to n to determine whether n is a square number or not. The returned values are:

0: When n is not expressed as a square of numbers from 1 to 1000.
1: When n is expressed as the square of one of the numbers from 1 to 1000
2: When n is greater than the square of numbers from 1 to 1000
