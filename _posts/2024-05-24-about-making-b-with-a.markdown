---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Making_B_With_A
title: Making B with A (with.Java)
# title: Making B with A (with.Java)
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
date: 2024-05-24 09:00:00 +0900
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

## This article looks into the problem of “Making B with A (with.Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When strings before and after are given as parameters, complete the solution function to return 1 if you can create after by changing the order of before, and 0 if you cannot.

#### Restrictions

- 0 < length of before == length of after < 1,000
- Before and after are both lowercase letters.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| before  | after   | result |
| ------- | ------- | ------ |
| "olleh" | "hello" | 1      |
| "allpe" | "apple" | 0      |

### My solution to the problem

```java
import java.util.Arrays;

class Solution {
 public int solution(String before, String after) {

 char[] beforeArray = before.toCharArray();
 char[] afterArray = after.toCharArray();
 Arrays.sort(beforeArray);
 Arrays.sort(afterArray);

 return Arrays.equals(beforeArray, afterArray) ? 1:0;
 }
}
```

### Solved review

First, convert the two input strings before and after into character arrays (char[]).

Sort an array of two characters alphabetically using the Arrays.sort() function.

This will ensure that each character in both strings is aligned.

Use the Arrays.equals() function to determine whether two sorted arrays of characters are equal.

This function compares two arrays for equality and returns true or false.

If the two sorted character arrays are equal, that is, if the two strings contain the same characters, it returns 1.

Otherwise it returns 0.

To simply check whether the input string consists of the same characters, we use a method of sorting and comparing strings.
