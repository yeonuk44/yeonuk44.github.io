---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Of_K
title: Number of k (with.Java)
# title: Number of k (with.Java)
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
date: 2024-05-25 09:00:00 +0900
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

## This is an article about the "Number of k (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

In the numbers 1 to 13, 1 appears 6 times: 1, 10, 11, 12, and 13.

When integers i, j, and k are given as parameters, complete the solution function to return how many times k appears from i to j.

#### Restrictions

- 1 ≤ i < j ≤ 100,000
- 0 ≤ k ≤ 9

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

<!-- | before | after | result |
| ------- | ------- | ------ |
| "olleh" | "hello" | 1 |
| "allpe" | "apple" | 0 | -->

| i   | j   | k   | result |
| --- | --- | --- | ------ |
| 1   | 13  | 1   | 6      |
| 10  | 50  | 5   | 5      |
| 3   | 10  | 2   | 0      |

### My solution to the problem

```java
class Solution {
 public int solution(int i, int j, int k) {
 int answer = 0;
 String str = "0";
 char ch = '0';
 for(int a = i; a <= j; a++){
 str = Integer.toString(a);
 for(int b = 0; b < str.length(); b++){
 ch = str.charAt(b);
 if(ch == Integer.toString(k).charAt(0)){
 answer++;
 }
 }
 }
 return answer;
 }
}
```

### Solved review

Set the answer variable to its initial value of 0.

This variable represents the result.

Initialize the str variable to "0". This variable is used to convert numbers into strings and store them.

Initialize the ch variable to '0'. This variable is used to check character by character in a string.

Execute the loop while increasing variable a from i to j.

Convert the value of a to a string and store it in the str variable.

Execute the loop while increasing the b variable from 0 to the length of str - 1.

Check the bth character (ch) of str.

If ch is equal to k, then increase the answer variable by 1.

When the loop ends, the answer variable is returned.

The code is implemented by converting each number within the input range into a string, checking each character of the string one by one, and comparing it with k.
