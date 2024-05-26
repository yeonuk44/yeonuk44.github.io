---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_String_Push
title: String push (with.Java)
# title: String push (with.Java)
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
date: 2024-05-26 09:00:00 +0900
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

## This is an article about the "String Pushing (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

In the string "hello", if we move each character one space to the right and move the last character to the front, we get "ohell".

If you define this as pushing a string, when strings A and B are given as parameters, complete the solution function so that if A can be pushed to become B, it returns the minimum number of times it must be pushed, and if it cannot be pushed to B, it returns -1.

#### Restrictions

- 0 < length of A = length of B < 100
- A and B are made up of lowercase alphabet letters.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| A       | B       | result |
| ------- | ------- | ------ |
| "hello" | "ohell" | 1      |
| "apple" | "elppa" | -1     |
| "atat"  | "tata"  | 1      |
| "abc"   | "abc"   | 0      |

### My solution to the problem

```java
class Solution {
 public int solution(String A, String B) {
 int answer = -1;
 StringBuilder sb = new StringBuilder(A);
 char[] chArr = A.toCharArray();
 int repeatCount = 1;

 if(A.equals(B)){
 return 0;
 }

 for(int i = chArr.length - 1; i >= 0; i--){
 sb.replace(0,0,Character.toString(chArr[i]));
 sb.deleteCharAt(sb.length() - 1);
 if(sb.toString().equals(B)){
 return repeatCount;
 }
 repeatCount++;
 }


 return answer;
 }
}
```

### Solved review

To solve the problem of finding the minimum number of rotations to rotate a string to create the desired string, we use a string manipulation method.

The above code is a function that, given two strings A and B, calculates the minimum number of rotations required to circularly move string A to create a string identical to B.

First, if the input strings A and B are the same, there is no need to rotate, so it returns 0.

Otherwise, manipulate the string A using StringBuilder.

Create an array of characters from string A and manipulate the string sequentially from back to front.

At each rotation, we loop through string A and compare it to B.

At the moment string A becomes equal to B, the number of rotations until now is returned.
If the loop through string A does not find a string identical to B, -1 is returned.
