---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_To_Come_Next
title: Number to come next (with.Java)
# title: Number to come next (with.Java)
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
date: 2024-05-29 09:00:00 +0900
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

## This is an article looking at the "Next Number (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When an arithmetic sequence or a geometric sequence common is given as a parameter, complete the solution function to return the number that comes after the last element.

#### Restrictions

- 2 < length of common < 1,000
- -1,000 < element of common < 2,000
- All elements of common are integers.
- There is no case where it is not an arithmetic sequence or a geometric sequence.
- In the case of a geometric sequence, the common ratio is an integer other than 0.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| common       | result |
| ------------ | ------ |
| [1, 2, 3, 4] | 5      |
| [2, 4, 8]    | 16     |

### My solution to the problem

```java
class Solution {
 public int solution(int[] common) {
 int answer = 0;
 if(common[1] - common[0] == common[2] - common[1]){
 answer = common[common.length - 1] + (common[1] - common[0]);
 }else{
 answer = common[common.length - 1] * (common[1] / common[0]);
 }
 return answer;
 }
}
```

### Solution review

This is a function that determines whether it is an arithmetic sequence or an arithmetic sequence and calculates the next term.

Checks whether the values ​​corresponding to indices 0, 1, and 2 of a given array form an arithmetic or geometric sequence.

If it is an arithmetic sequence, the next term is obtained by adding (the arithmetic value) to the last element of the array.

If it is a geometric sequence, multiply the last element of the array by (the value of the common ratio) to get the next term.

Returns the obtained value.
