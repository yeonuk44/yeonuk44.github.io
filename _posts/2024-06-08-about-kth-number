---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Kth_Number
title: Kth number (with.Java)
# title: Kth number (with.Java)
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
date: 2024-06-08 09:00:00 +0900
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

## This is an article about the "Kth number (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When cutting and sorting from the i-th number to the j-th number of an array, we want to find the k-th number.

For example, if array is [1, 5, 2, 6, 3, 7, 4], i = 2, j = 5, k = 3

If you cut the 2nd to 5th positions in the array, you get [5, 2, 6, 3].

Sorting the array from 1 is [2, 3, 5, 6].

The third number in the array from 2 is 5.

When an array array, a two-dimensional array commands with [i, j, k] as elements, is given as a parameter, write a solution function to return the result of applying the operation described above to all elements of commands in an array. Please.

#### Restrictions

- The length of the array is between 1 and 100.
- Each element of the array is between 1 and 100.
- The length of commands is between 1 and 50.
- Each element of commands has length 3.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| array                 | commands                          | return    |
| --------------------- | --------------------------------- | --------- |
| [1, 5, 2, 6, 3, 7, 4] | [[2, 5, 3], [4, 4, 1], [1, 7, 3]] | [5, 6, 3] |

### My solution to the problem

```java
import java.util.Arrays;

class Solution {
 public int[] solution(int[] array, int[][] commands) {
 int[] answer = new int[commands.length];
 for(int i = 0; i < commands.length; i++){
 int[] tempArr = Arrays.copyOfRange(array, commands[i][0] - 1, commands[i][1]);
 Arrays.sort(tempArr);
 answer[i] = tempArr[commands[i][2] - 1];
 }
 return answer;
 }
}
```

### Solved review

The solution method receives an integer array array and a two-dimensional integer array commands as input.

Create an integer array answer to store the results. It is set to the same size as the commands array.

Iterates through the commands array and processes each command.

Each command cuts the array into a specific section, sorts the section, and extracts the value at a specific position.

Use the Arrays.copyOfRange() method to create a new array by copying the corresponding range from the given array.

Sort the copied array using the Arrays.sort() method.

Store the value at position commands[i][2] - 1 in the sorted array into answer[i]. Note that the array index starts from 0, so 1 must be subtracted from the position value of the command.

When all commands are processed, an answer array is returned.

This code solves the problem of cutting and sorting an array according to each instruction, then extracting and returning the value at a specific position.
