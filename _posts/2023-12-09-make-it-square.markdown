---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Make_It_Square
title: Make it square (with.Java)
# title: Make it square (with.Java)
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
date: 2023-12-09 09:00:00 +0900
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

## This is the "Make it square" problem.

We're going to learn by solving coding test problems, reflecting on the problems we've solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

A two-dimensional array of integers, arr, is given as a parameter.

Write a solution function that returns a two-dimensional array with zeros added to the end of each row so that the number of columns equals the number of rows if arr has more rows, and zeros added to the end of each column so that the number of columns equals the number of rows if arr has more columns.

#### Example input and output

| arr                                                              | result                                                                       |
| ---------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [[572, 22, 37], [287, 726, 384], [85, 137, 292], [487, 13, 876]] | [[572, 22, 37, 0], [287, 726, 384, 0], [85, 137, 292, 0], [487, 13, 876, 0]] |

My solution to the ### problem

```java
import java.util.*;
class Solution {
    public int[][] solution(int[][] arr) {
        int numRows = arr.length;
        int numCols = arr[0].length;

        if (numRows < numCols) {
            int[][] result = new int[numCols][numCols];
            for (int i = 0; i < numRows; i++) {
                result[i] = Arrays.copyOf(arr[i], numCols);
            }
            for (int i = numRows; i < numCols; i++) {
                result[i] = new int[numCols];
            }
            } return result;
        }
        else if (numCols < numRows) {
            int[][] result = new int[numRows][numRows];
            for (int i = 0; i < numRows; i++) {
                result[i] = Arrays.copyOf(arr[i], numRows);
            }
    } return result;
}return arr;
```

#### Solution Explanation

int numRows = arr.length; and int numCols = arr[0].length;: count the number of rows and columns in the array.

if (numRows < numCols): if the number of rows is less than the number of columns (if there are fewer rows):

int[][] result = new int[numCols][numCols];: create a new square array result.

for (int i = 0; i < numRows; i++) : Copy the rows of the existing array. The rows of the array arr are copied to the rows of result, and the remaining columns are initialized to zero.

for (int i = numRows; i < numCols; i++) : Create and initialize a new array for the remaining columns.

else if (numCols < numRows) : if the number of columns is less than the number of rows (if there are fewer columns):

int[][] result = new int[numRows][numRows];: create a new square array result.

for (int i = 0; i < numRows; i++) : Copy the rows of the existing array. Copy the rows of the array arr into the rows of result.

return arr;: If arr is already square, return the original array arr as it is. Translated with www.DeepL.com/Translator (free version)
