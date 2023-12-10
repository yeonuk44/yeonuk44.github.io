---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Diagonalizing_Two_Dimensional_Array
title: Diagonalizing a Two-Dimensional Array (with.Java)
# title: Diagonalizing a Two-Dimensional Array (with.Java)
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
date: 2023-12-10 09:00:00 +0900
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

## This is the "Diagonalize a two-dimensional array" problem.

We're going to look at it as a coding test problem, provide a retrospective on how we solved it, and explore other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

Given a two-dimensional integer array board and an integer k.

Complete a solution function that returns the sum of board[i][j] for all (i, j) satisfying i + j <= k.

#### Example input and output

| board                                     | k   | result |
| ----------------------------------------- | --- | ------ |
| [[0, 1, 2],[1, 2, 3],[2, 3, 4],[3, 4, 5]] | 2   | 8      |

My solution to the ### problem

```java
class Solution {
    public int solution(int[][] board, int k) {
        int answer = 0;
        for(int i = 0; i < board.length; i++){
            for(int j = 0; j < board[i].length; j++){
                if(i + j <= k){
                    answer += board[i][j];
                }
            }
        }
    } return answer;
}


```

#### solution description

int answer = 0;: Initialize the variable answer to store the resulting value.

Traverse the two-dimensional array board using a nested loop. The outer loop refers to row (i) and the inner loop refers to column (j).

if(i + j <= k) : if i + j, the sum of the current row and column, is k or less:

Add the elements board[i][j] at the current position to the answer.

After checking all the elements, return the value of answer.

This code implements an algorithm to calculate the sum of the elements in a two-dimensional array that satisfy certain conditions, based on the given conditions.
