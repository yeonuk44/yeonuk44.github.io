---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sum_Of_Consecutive_Numbers
title: Sum of consecutive numbers (with.Java)
# title: Sum of consecutive numbers (with.Java)
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
date: 2024-05-28 09:00:00 +0900
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

## This is an article about the "Sum of consecutive numbers (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Three consecutive integers that add up to 12 are 3, 4, and 5.

You are given two integers num and total.

Complete the solution function so that when the sum of num consecutive numbers becomes total, it returns an array of integers in ascending order.

#### Restrictions

- 1 ≤ num ≤ 100
- 0 ≤ total ≤ 1000
- There is no test case in which total cannot be obtained by adding num consecutive numbers.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| num | total | result           |
| --- | ----- | ---------------- |
| 3   | 12    | [3, 4, 5]        |
| 5   | 15    | [1, 2, 3, 4, 5]  |
| 4   | 14    | [2, 3, 4, 5]     |
| 5   | 5     | [-1, 0, 1, 2, 3] |

### My solution to the problem

```java
class Solution {
 public int[] solution(int num, int total) {
 int[] answer = new int[num];
 int startNum = total / num - (num - 1) / 2;

 for(int i = 0; i < num; i++){
 answer[i] = startNum++;
 }
 return answer;
 }
}
```

### Solution review

This function generates numbers at regular intervals starting from the starting number, given the sum of the starting number and the total number.

The solution function takes two parameters: num and total.

First, we create an array answer to store the results. The length of this array is set to num.

Initialize the startNum variable to calculate the starting number. This value is calculated by dividing the given total number by the given number and then subtracting (number of numbers - 1) / 2 from that value. This allows numbers to be generated at regular intervals.

Use loops to assign each element a value that starts with a starting number and increases at regular intervals.
Returns the result array answer.
