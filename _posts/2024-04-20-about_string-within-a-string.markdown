---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_String_Within_A_String
title: String within a string (with, Java)
# title: String within a string (with, Java)
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
date: 2024-04-20 09:00:00 +0900
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

## This is an article that looks into the problem of “strings within strings (with, Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

String str1, str2 are given as parameters.

Complete the solution function so that it returns 1 if str2 is in str1, or 2 if not.

#### Restrictions

- 1 ≤ length of str1 ≤ 100
- 1 ≤ length of str2 ≤ 100
- The string consists of uppercase letters, lowercase letters, and numbers.

#### Input/Output Example

<!-- | n | result |
| ------ | ------ |
| 1234 | 10 |
| 930211 | 16 | -->

| str1                     | str2   | result |
| ------------------------ | ------ | ------ |
| "ab6CDE443fgh22iJKlmn1o" | "6CD"  | 1      |
| "ppprrogrammers"         | "pppp" | 2      |
| "AbcAbcA"                | "AAA"  | 2      |

### My solution to the problem

```java
class Solution {
     public int solution(String str1, String str2) {
         int answer = 0;
         if(str1.contains(str2)){
             answer = 1;
         }else{
             answer = 2;
         }
         return answer;
     }
}
```

### Solution explanation

public int solution(String str1, String str2): Define a method named solution and receive two strings str1 and str2 as parameters. Returns an integer value.

int answer = 0;: Initialize the variable answer, which will store the result, to 0.

if(str1.contains(str2)): If str1 contains str2,
answer = 1;: Assign 1 to answer.

else: Otherwise,
answer = 2;: Assign 2 to answer.

return answer;: Finally returns the answer value.
