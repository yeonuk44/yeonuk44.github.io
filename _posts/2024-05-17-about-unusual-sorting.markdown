---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Unusual_Sorting
title: Unusual sorting (with.Java)
# title: Unusual sorting (with.Java)
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
date: 2024-05-17 09:00:00 +0900
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

## This article looks into the "unusual sorting (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

We want to sort the numbers closest to n based on the integer n.

At this time, if the distance from n is the same, place the larger number first.

Given an array of integers, numlist, and an integer n, complete the solution function so that it returns an array that sorts the elements of numlist in order of proximity to n.

#### Restrictions

- 1 ≤ n ≤ 10,000
- 1 ≤ elements of numlist ≤ 10,000
- 1 ≤ length of numlist ≤ 100
- numlist does not have duplicate elements.

#### Input/Output Example

<!-- | lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| numlist                       | n   | result                               |
| ----------------------------- | --- | ------------------------------------ |
| [1, 2, 3, 4, 5, 6]            | 4   | [4, 5, 3, 6, 2, 1]                   |
| [10000,20,36,47,40,6,10,7000] | 30  | [36, 40, 20, 47, 10, 6, 7000, 10000] |

### My solution to the problem

```java
import java.util.*;
class Solution {
 public int[] solution(int[] numlist, int n) {
 int[] answer = new int[numlist.length];
 int absValue = 0;
 int temp = Integer.MAX_VALUE;
 int idx = 0;
 Arrays.sort(numlist);

 ArrayList<Integer> arr_new = new ArrayList<Integer>();
 for (int i : numlist){
 arr_new.add(i);
 }


 for(int i = 0; i < answer.length; i++){
 for(int j = arr_new.size() - 1; j >= 0; j--){
 absValue = Math.abs(n - arr_new.get(j));
 if(temp > absValue){
 temp = absValue;
 idx = j;
 }
 }
 answer[i] = arr_new.get(idx);
 temp = Integer.MAX_VALUE;
 arr_new.remove(arr_new.get(idx));
 }
 return answer;
 }
}
```

### Solution explanation

Sorts the given array numlist.

Initialize the array answer to store the correct answer.

Creates an ArrayList arr_new to store each element of the array numlist, and adds each element of the sorted numlist to arr_new.

Calculates the difference between n and the current element and stores it in absValue.

If absValue is less than the minimum value temp so far, temp is updated to absValue and the current index idx is set to the index of the element.

Store the closest number found using temp and idx in answer.

Remove that number from arr_new.

When the iteration is complete, it returns an answer.
