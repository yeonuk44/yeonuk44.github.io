---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_Location_A_Point
title: Finding the location of a point (with.Java)
# title: Finding the location of a point (with.Java)
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
date: 2024-02-07 09:00:00 +0900
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

## This is an article about the problem of “Finding the location of a point.”

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

A quadrant is a plane divided into four parts based on the x and y axes.

The quadrants are numbered 1 through 4 as shown below.

If both the x and y coordinates are positive, it is in the first quadrant.

If the x-coordinate is negative and the y-coordinate is positive, it belongs to the second quadrant.

If both the x and y coordinates are negative, it is in the third quadrant.

If the x-coordinate is positive and the y-coordinate is negative, it belongs to the fourth quadrant.

An integer array dot containing the x coordinates (x, y) in order is given as a parameter.

Please complete the solution function to return one of 1, 2, 3, or 4 to indicate which quadrant the coordinate dot belongs to.

#### Restrictions

- Length of dot = 2
- dot[0] represents the x-coordinate, and dot[1] represents the y-coordinate.
- -500 ≤ element of dot ≤ 500
- The element of dot is not 0.

#### Input/Output Example

| dot     | result |
| ------- | ------ |
| [2, 4]  | 1      |
| [-7, 9] | 2      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int[] dot) {
         int answer = 0;

         if(dot[0] > 0 && dot[1] > 0){
             answer = 1;
         }else if(dot[0] < 0 && dot[1] > 0){
             answer = 2;
         }else if(dot[0] < 0 && dot[1] < 0){
             answer = 3;
         }else if(dot[0] > 0 && dot[1] < 0){
             answer = 4;
         }
         return answer;
     }
}
```

### Solution explanation

This code determines and returns the quadrant to which the given coordinate dot belongs.

No special function is used, and the quadrant is determined through the given conditional statement and the value is stored in the answer.

The main concept used here is the division of quadrants in the coordinate plane.

Each conditional statement means:

dot[0] > 0 && dot[1] > 0: Quadrant 1
dot[0] < 0 && dot[1] > 0: Quadrant 2
dot[0] < 0 && dot[1] < 0: 3rd quadrant
dot[0] > 0 && dot[1] < 0: Quadrant 4

**Benefits of this code**

Simple and clear logic: Easy to understand by explicitly expressing given conditions.

Performance: It is very efficient because determination of each condition is made sequentially.

**disadvantage**

In some cases, the size of the dot array may be incorrect.

There is no handling for these situations. (e.g. when dot.length is not 2)
