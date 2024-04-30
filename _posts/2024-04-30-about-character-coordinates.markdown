---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Character_Coordinates
title: Creating maximum value 2 (with.Java)
# title: Creating maximum value 2 (with.Java)
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
date: 2024-04-30 09:00:00 +0900
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

## This article looks into the problem of “Creating the maximum value 2 (with.Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The integer array numbers is given as a parameter.

Complete the solution function to return the maximum value that can be created by multiplying two of the elements of numbers.

#### Restrictions

- -10,000 ≤ elements of numbers ≤ 10,000
- 2 ≤ length of numbers ≤ 100

#### Input/Output Example

<!-- | keyinput | board | result |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1] |
| ["down", "down", "down", "down", "down"] | [7, 9] | [0, -4] | -->

| numbers                   | result |
| ------------------------- | ------ |
| [1, 2, -3, 4, -5]         | 15     |
| [0, -31, 24, 10, 1, 9]    | 240    |
| [10, 20, 30, 5, 5, 20, 5] | 600    |

### My solution to the problem

```java
import java.util.Arrays;

class Solution {
 public int solution(int[] numbers) {
 Arrays.sort(numbers);

 int n = numbers.length;
 int maxNegative = numbers[0] * numbers[1];
 int maxPositive = numbers[n - 1] * numbers[n - 2];

 return Math.max(maxNegative, maxPositive);
 }
}

```

### Solution explanation

- Array sorting: Sorts the given array to distinguish between negative and positive numbers.
- Select the two largest negative numbers: Select the first and second elements of the sorted array and calculate the product of the two largest negative numbers.
- Select the two largest positive numbers: Select the last and second-to-last elements of the sorted array and calculate the product of the two largest positive numbers.
- Return result: Returns the larger value of the product of a negative number and a positive number.

**Code Advantages**

- Simple logic: I used a simple method of sorting an array, picking the largest number and the second largest number and multiplying them.
- Efficiency through sorting: We implemented the process of selecting the largest number quickly and simply using a sorted array.

**Code Disadvantages**

- Time complexity due to array sorting: The time complexity for the process of sorting an array is O(n log n), which may affect performance if the array is large.
