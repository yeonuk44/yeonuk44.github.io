---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Rotating_Array
title: Rotating an array (with.Java)
# title: Rotating an array (with.Java)
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
date: 2024-02-09 09:00:00 +0900
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

## This is an article about the "rotating array" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

An array containing integers numbers and a string direction are given as parameters.

Complete the solution function so that it returns an array in which the elements of the array numbers are rotated one by one in the direction direction.

#### Restrictions

- 3 ≤ length of numbers ≤ 20
- direction is either "left" or "right".

#### Input/Output Example

| numbers                   | direction | result                    |
| ------------------------- | --------- | ------------------------- |
| [1, 2, 3]                 | "right"   | [3, 1, 2]                 |
| [4, 455, 6, 4, -1, 45, 6] | "left"    | [455, 6, 4, -1, 45, 6, 4] |

|

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int[] solution(int[] numbers, String direction) {
         int[] answer = new int[numbers.length];
         if(direction.equals("right")){
             for(int i = 0; i < numbers.length; i++){
                 if(answer.length == i + 1){
                     answer[0] = numbers[i];
                 }else{
                     answer[i + 1] = numbers[i];
                 }
             }
         }else{
             for(int i = 0; i < numbers.length; i++){
                 if(answer.length == i + 1){
                     answer[i] = numbers[0];
                 }else{
                     answer[i] = numbers[i + 1];
                 }
             }
         }
         return answer;
     }
}
```

### Solution explanation

If the given direction is "right": Move each element of the array to the right by one space.

The last element moves to the first element.

If the given direction is "left": Move each element of the array to the left by one space.

The first element moves to the last element.

Performing the above two actions will allow you to rotate the array.

**Description of functions used**
equals(): A method that compares strings.

The reason you do not use the == operator when comparing strings is because strings are reference types.

The equals() method allows you to compare the actual contents of two strings.

**Code Analysis**
I am comparing strings using equals() method.

direction.equals("right") and direction.equals("left") are conditional statements that check whether the given direction is "right" or "left".

I am rotating an array through a for loop.

When moving right, the last element is moved first, and when moving left, the first element is moved last.

**Code Advantages**
Using the equals() method: When comparing strings, by using the equals() method, we are comparing the contents of the actual strings.

Because strings are reference types, it is correct to use equals() to compare contents.
