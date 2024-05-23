---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Binary_Addition
title: Binary addition (with.Java)
# title: Binary addition (with.Java)
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
date: 2024-05-23 09:00:00 +0900
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

## This is an article about the "Binary number addition (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When two strings bin1 and bin2, which represent binary numbers, are given as parameters, complete the solution function to return the sum of the two binary numbers.

#### Restrictions

- The return value is a string meaning a binary number.
- 1 ≤ bin1, length of bin2 ≤ 10
- bin1 and bin2 consist of only 0 and 1.
- bin1 and bin2 do not start with zeros except "0".

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| bin1   | bin2   | result  |
| ------ | ------ | ------- |
| "10"   | "11"   | "101"   |
| "1001" | "1111" | "11000" |

### My solution to the problem

```java
class Solution {
 public String solution(String bin1, String bin2) {
 String answer = "";
 int binarySum = Integer.parseInt(bin1,2) + Integer.parseInt(bin2,2);

 answer = Integer.toBinaryString(binarySum);

 return answer;
 }
}
```

### Solved review

This function takes two binary strings as input, converts them to decimal, and returns the summed result back as a binary string.

First, we initialize the answer variable to an empty string.

Using the Integer.parseInt() function, convert the two input binary strings (bin1 and bin2) to decimal numbers and then add them. This calculates the sum of two binary numbers as a decimal number.

To convert the binary sum back to a binary string, we use the Integer.toBinaryString() function. This function converts a decimal number to a binary string.

Assigns the converted binary string to the answer variable and returns it.
