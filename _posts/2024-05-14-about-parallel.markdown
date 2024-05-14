---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Parallel
title: Parallel (with.Java)
# title: Parallel (with.Java)
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
date: 2024-05-14 09:00:00 +0900
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

## This article looks into the "parallel (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

A two-dimensional array dots containing the coordinates of four points is given as a parameter as follows.

[[x1, y1], [x2, y2], [x3, y3], [x4, y4]]

Complete the solution function so that when the given four points are divided into two, if the two straight lines are parallel, it returns 1, and if not, it returns 0.

#### Restrictions

- Length of dots = 4
- The elements of dots are in the form [x, y], where x and y are integers.
- 0 ≤ x, y ≤ 100
- There is no case where two or more different points overlap.
- Even if two straight lines overlap (coincide), please return 1.
- It is not given if the straight line connecting any two points is parallel to the x-axis or y-axis.

#### Input/Output Example

<!-- | keyinput | board | result |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1] |
| ["down", "down", "down", "down", "down"] | [7, 9] | [0, -4] | -->

| dots                              | result |
| --------------------------------- | ------ |
| [[1, 4], [9, 2], [3, 8], [11, 6]] | 1      |
| [[3, 5], [4, 1], [2, 4], [5, 10]] | 0      |

### My solution to the problem

```java
class Solution {
     public int solution(int[][] dots) {
         int answer = 0;
         for(int i =0; i<dots.length;i++) {

                 float temp =gradient(dots[i],dots[(i+1)%4]);
                 float temp2 =gradient(dots[(i+2)%4],dots[(i+3)%4]);

                 if(temp==temp2) {
                     answer = 1;
                 }
         }
         return answer;
     }
     public static float gradient(int[]a1,int[]a2) {
         float denom, mole;

             denom=a1[0]-a2[0];
             mole=a1[1]-a2[1];

         return mole/denom;
     }
}
```

### Solution explanation

The solution method takes a given array of points, dots, as an argument.

The answer variable stores the result indicating whether it is square or not.

It is initially set to 0.

A for loop iterates over an array of dots.

At this time, based on the ith point, the slopes between the other three points excluding that point are compared.

The gradient method calculates the gradient between two points. This allows you to find the slope of the line formed by two points.

If all sides have the same slope (temp and temp2 are the same), set answer to 1.

After completing all loops, the answer value is returned.

Provides a simple method to check whether a square is formed using given points.

Although the number of points and the shape of the array may change depending on the given problem, you can use the method to determine the shape of the polygon.
