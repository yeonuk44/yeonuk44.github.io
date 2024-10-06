---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Integer_Triangle
title: Integer triangle (with.Java)
# title: Integer triangle (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, dp]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-06 09:00:00 +0900
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

## This is an article about an integer triangle (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

In the path from the top to the bottom of the above triangle, we want to find the case where the sum of the numbers passed is the largest.

When moving to the lower compartment, you can only move one compartment diagonally to the right or left.

For example, in 3, you can only move to 8 or 1 in the lower compartment.

Complete the solution function so that the maximum value of the number passed can be returned, given the triangle's information array triangle as a parameter

#### Restrictions

- The height of the triangle is greater than 1 and less than 500.
- The number that makes up a triangle is an integer greater than 0 and less than 9,999.

#### Input/output Examples

| triangle                                                | result |
| ------------------------------------------------------- | ------ |
| [[7], [3, 8], [8, 1, 0], [2, 7, 4, 4], [4, 5, 2, 6, 5]] | 30     |

### problem solving

```java
class Solution {
    public int solution(int[][] triangle) {
        int answer = 0;

        for(int i = 1; i < triangle.length; i++){
            for(int j = 0; j < triangle[i].length; j++){
                // left-hand calculation
                if(j == 0){
                    triangle[i][j] += triangle[i - 1][j];
                }
                // right-hand calculation
                // 1 1 = 0 0
                else if(j == i){
                    triangle[i][j] += triangle[i - 1][j - 1];
                }
                // central calculation
                else{
                    // 2 1 = 1 0 | 1 1
                    // 3 1 = 2 0 | 2 1
                    triangle[i][j] += Math.max(triangle[i - 1][j - 1], triangle[i - 1][j]);
                }
            }
        }

        int len = triangle.length;
        for(int i = 0; i < len; i++){
            if(answer < triangle[len - 1][i]){
                answer = triangle[len - 1][i];
            }
        }

        return answer;
    }
}
```

#### Solution Description

This is the problem of finding and returning values that maximize the sum of the paths in a given triangular array.

Use dynamic programming to solve it.

First, initialize the variable answer.

This variable stores the maximum sum to finally return.

We now use the double for loop to update the triangular array.

The first for loop traverses from the second row to the last row of a triangle.

The second for loop traverses all columns of the current row.

Here's how to calculate the maximum path sum at each location.

First, the calculation on the left. If the current position is the first element in the row, add the element immediately above.

Next, calculate to the right. If the current position is the last element of the row, add the diagonal left element above.

Finally, the central calculation. If the current position is in the middle of the row, add the larger of the two diagonal elements above.

You must now find the maximum value in the last row.

It traverses all elements of the last row and finds the maximum value, and returns this maximum value.

Dynamic programming can be used to obtain the maximum path sum from a triangular array.
