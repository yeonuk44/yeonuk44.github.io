---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Special_Two_Dimensional_Array_1
title: Special two-dimensional array 1 (with.Java)
# title: Special two-dimensional array 1 (with.Java)
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
date: 2023-12-02 09:00:00 +0900
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

## This is a recap of the "Special two-dimensional array 1" problem.

We're going to learn about it by solving coding test problems, reflecting on the problems we've solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

Write a solution function that, given an integer n as a parameter, returns a two-dimensional array arr of size n × n that looks like this

The value of arr[i][j] (0 ≤ i, j < n) is 1 if i = j and 0 otherwise.

#### Example input and output

| n   | result                                                                                                                            |
| --- | --------------------------------------------------------------------------------------------------------------------------------- |
| 3   | [[1, 0, 0], [0, 1, 0], [0, 0, 1]]                                                                                                 |
| 6   | [[1, 0, 0, 0, 0, 0, 0, 0], [0, 1, 0, 0, 0, 0, 0], [0, 0, 1, 0, 0, 0], [0, 0, 0, 1, 0, 0], [0, 0, 0, 0, 1, 0], [0, 0, 0, 0, 0, 1]] |
| 1   | [[1]]                                                                                                                             |

My solution to the ### problem

```java
class Solution {
    public int[][] solution(int n) {
        int[][] answer = new int[n][n];
        for(int i = 0; i < n; i++){
            for(int j = 0; j < n; j++){
                if(i == j){
                    answer[i][j] = 1;
                }else {
                    answer[i][j] = 0;
                }
            }
        }
    } return answer;
}
```

#### Solution

int[][] answer = new int[n][n];: create a two-dimensional array answer of size n x n.

for(int i = 0; i < n; i++) : Iterate through the rows of the array, with the value of i representing the current row.

for(int j = 0; j < n; j++) : Iterates through the columns of the array, with the value of j representing the current column.

if(i == j) : if the current row and column have the same index (main diagonal element):

Store 1 in the array element at that position.

else : Otherwise (non-major diagonal element):

Store a 0 in the array element at that position.

return answer;: Returns a two-dimensional array answer initialized with the unit matrix.
