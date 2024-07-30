---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Phoneketmon
title: Phoneketmon (with.Java)
# title: Phoneketmon (with.Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, hash]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-05-31 09:00:00 +0900
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

## This is an article about the "Phoneketmon (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

After a long journey to catch Pokémon, you arrived at Dr. Hong's laboratory.

Dr. Hong said you could take N/2 of the total N Pokémon in his lab.

The Pokemon in Dr. Hong's lab are numbered according to their type. Therefore, Pokemon of the same type have the same number.

For example, if there are a total of 4 Pokémon in the laboratory, and the type number of each Pokémon is [3, 1, 2, 3], this means two Pokémon with number 3, one Pokémon with number 1, Indicates that there is one Pokémon number 2.

At this time, there are 6 ways to select 2 out of 4 Pokémon:

- Select the first (No. 3) and second (No. 1) Pokemon
- Select the first (No. 3) and third (No. 2) Pokémon
- Select the first (No. 3) and fourth (No. 3) Pokémon
- Select the second (No. 1) and third (No. 2) Pokemon
- Select the second (No. 1) and fourth (No. 3) Pokemon
- Select the third (No. 2) and fourth (No. 3) Pokémon

At this time, the method of selecting the first (No. 3) Pokemon and the fourth (No. 3) Pokemon allows you to have only one type of Pokemon (two No. 3 Pokemon), but all other methods only allow you to have two types of Pokemon. You can have Kemon.

Therefore, in the example above, the maximum number of Pokémon types you can have is 2.

Since you want to have as many different types of Pokemon as possible, you want to choose N/2 Pokemon, including as many different types of Pokemon as possible.

When an array nums containing the type numbers of N Pokemon is given as a parameter, among the methods of selecting N/2 Pokemon, find the method that selects the most types of Pokemon and select the Pokemon type number at that time. Please complete the solution function to return the number of.

#### Restrictions

- nums is a one-dimensional array containing the Pokemon type number.
- The length (N) of nums is a natural number between 1 and 10,000, and is always given as an even number.
- The Pokémon type number is expressed as a natural number between 1 and 200,000.
- Even if there are multiple ways to select the largest type of Pokemon, you only need to return the maximum number of Pokemon types that can be selected.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| nums               | result |
| ------------------ | ------ |
| [3, 1, 2, 3]       | 2      |
| [3, 3, 3, 2, 2, 4] | 3      |
| [3, 3, 3, 2, 2, 2] | 2      |

### My solution to the problem

```java
import java.util.Arrays;
class Solution {
 public int solution(int[] nums) {
 int answer = 0;
 int choiceNum = nums.length / 2;
 nums = Arrays.stream(nums).distinct().toArray();

 if(nums.length >= choiceNum){
 return choiceNum;
 }else{
 return nums.length;
 }
 }
}
```

### Solved review

The solution method takes as input the integer array nums.

Declare a choiceNum variable and store half the length of the array. This represents the maximum number of numbers that can be selected.

Use Arrays.stream(nums).distinct().toArray() to remove duplicate numbers, then convert to an array and store it in nums.

If the length of the deduplicated array using an if statement is greater than or equal to choiceNum, it returns choiceNum. This means that the length of the deduplicated array is greater than the maximum number of numbers that can be selected.

Otherwise, it returns the length of the array with duplicates removed.

Returns the number of numbers finally selected.

This code uses a simple method to remove duplicate numbers from an array and return the number of different numbers based on the maximum number of numbers that can be selected.
