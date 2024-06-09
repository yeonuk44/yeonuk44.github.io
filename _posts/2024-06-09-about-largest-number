---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Largest_Number
title: Largest number (with. Java)
# title: Largest number (with. Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, sort]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-06-09 09:00:00 +0900
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

## This is an article about the "largest number (with. Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Given 0 or a positive integer, find the largest number that can be created by concatenating the integers.

For example, given the integers [6, 10, 2], we can create [6102, 6210, 1062, 1026, 2610, 2106], of which the largest number is 6210.

When an array numbers containing 0 or positive integers is given as a parameter, write a solution function to convert the largest number that can be created by rearranging the order into a string and return it.

#### Restrictions

- The length of numbers must be between 1 and 100,000.
- The elements of numbers are between 0 and 1,000.
- The correct answer may be too large, so convert it to a string and return it.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| numbers           | return    |
| ----------------- | --------- |
| [6, 10, 2]        | "6210"    |
| [3, 30, 34, 5, 9] | "9534330" |

### My solution to the problem

```java
import java.util.Arrays;

class Solution {
 public String solution(int[] numbers) {
 String[] answer = new String[numbers.length];

 for(int i = 0; i < numbers.length; i++){
 answer[i] = String.valueOf(numbers[i]);
 }

 Arrays.sort(answer, (m1, m2) -> (m2 + m1).compareTo(m1 + m2));

 if(answer[0].equals("0")){
 return "0";
 }

 return String.join("", answer);
 }
}
```

### Solved review

The solution method takes the integer array numbers as input.

Create a string array answer to store the results. The size of this array is equal to the length of the numbers array.

Use a for loop to convert each element of the numbers array to a string and store it in the answers array.

Sort the answer array using Arrays.sort(). The sorting criteria compares the sizes of numbers created by combining given numbers.

The comparison standard is set so that when two strings are combined and compared, the larger value comes first. That is, it compares m2 + m1 and m1 + m2 and sorts them in descending order.

If the first element of the sorted array is "0", it returns "0" because the given number consists of all 0's.

Otherwise, use the String.join() method to join the sorted array and return it.

This code solves the problem of returning the largest number that can be created by combining a given array of numbers as a string.
