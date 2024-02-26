---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Changing_Index
title: Changing index (with.Java)
# title: Changing index (with.Java)
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
date: 2024-02-26 09:00:00 +0900
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

## This article looks into the "changing index" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When the string my_string and the integers num1 and num2 are given as parameters, complete the solution function to return a string with the characters corresponding to index num1 and index num2 in my_string changed.

#### Restrictions

- 1 < length of my_string < 100
- 0 ≤ num1, num2 < length of my_string
- my_string consists of lowercase letters.
- num1 ≠ num2

#### Input/Output Example

| my_string    | num1 | num2 | result       |
| ------------ | ---- | ---- | ------------ |
| "hello"      | 1    | 2    | "hlelo"      |
| “I love you” | 3    | 6    | "I l veoyou" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public String solution(String my_string, int num1, int num2) {
         char[] ch = my_string.toCharArray();

         ch[num1] = my_string.charAt(num2);
         ch[num2] = my_string.charAt(num1);

         String answer = String.valueOf(ch);
         return answer;
     }
}
```

### Solution explanation

- First, convert the given string to a char array. And replace the character at position ch[num1] with my_string.charAt(num2), and replace the character at position ch[num2] with my_string.charAt(num1).
- After completing the character exchange, convert the char array back to a string and store it in the answer variable. Finally, it returns an answer.
- In other words, the solution method performs a function that returns the result of exchanging the characters at positions num1 and num2 in the given string.
