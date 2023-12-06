---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Spiralizing_Integers
title: Spiralizing integers (with.Java)
# title: Spiralizing integers (with.Java)
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
date: 2023-12-05 09:00:00 +0900
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

## This is a recap of the "Arrange integers in a spiral" problem.

We're going to learn by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

A positive integer n is given as a parameter.

Write a solution function that returns a two-dimensional array containing the integers 1 through n2 in an n × n array, placed in a clockwise spiral from index [0][0].

#### Example input and output

| n   | result                                                                                                |
| --- | ----------------------------------------------------------------------------------------------------- | --- |
| 4   | [[1, 2, 3, 4], [12, 13, 14, 5], [11, 16, 15, 6], [10, 9, 8, 7]]                                       |
| 5   | [[1, 2, 3, 4, 5], [16, 17, 18, 19, 6], [15, 24, 25, 20, 7], [14, 23, 22, 21, 8], [13, 12, 11, 10, 9]] | }   |

My solution to the ### problem

```java
public class Solution {
    public int[][] solution(int n) {
        int[][] result = new int[n][n];

        int num = 1;
        int rowStart = 0, rowEnd = n - 1;
        int colStart = 0, colEnd = n - 1;

        while (num <= n * n) {
            for (int i = colStart; i <= colEnd; i++) {
                result[rowStart][i] = num++;
            }
            rowStart++;
            for (int i = rowStart; i <= rowEnd; i++) {
                result[i][colEnd] = num++;
            }
            colEnd--;
            for (int i = colEnd; i >= colStart; i--) {
                result[rowEnd][i] = num++;
            }
            rowEnd--;
            for (int i = rowEnd; i >= rowStart; i--) {
                result[i][colStart] = num++;
            }
            } colStart++;
    }

} return result;
```

#### solution

int[][] result = new int[n][n];: Create a two-dimensional array result of size n x n.

int num = 1;: Initialize the number.

int rowStart = 0, rowEnd = n - 1; and int colStart = 0, colEnd = n - 1;: Initialize the start and end indices of the rows and columns.

while (num <= n \* n): iterates while the number num is less than or equal to n x n.

for (int i = colStart; i <= colEnd; i++) : Fills in the numbers in the top row of the current matrix, moving from left to right.

Store num in result[rowStart][i] and increment num.

rowStart++;: After filling the top row, move to the next row.

Now fill the numbers in the right column, moving from top to bottom, then the left row, moving from right to left, then the bottom row, moving from top to bottom.

At each step, num is incremented by 1 and the start and end indices of the rows and columns are adjusted.

return result;: Returns a two-dimensional array result with all elements filled with numbers.

This code uses an efficient spiral pattern to create a two-dimensional array and populate it with numbers from 1 to n x n.
