---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Special_Two_Dimensional_Array_2
title: Special two-dimensional array 2 (with.Java)
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
date: 2023-12-03 09:00:00 +0900
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

## This is the "Special Two-Dimensional Array 2" problem.

We're going to learn about it by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

Given a two-dimensional array arr of size n × n as a parameter, write a solution function that returns 1 if arr satisfies the following and 0 otherwise.

arr[i][j] = arr[j][i] for any integer i, j such that 0 ≤ i, j < n.

#### Example input and output

| arr                                                                               | result |
| --------------------------------------------------------------------------------- | ------ |
| [[5, 192, 33], [192, 72, 95], [33, 95, 999]]                                      | 1      |
| [[19, 498, 258, 587], [63, 93, 7, 754], [258, 7, 1000, 723], [587, 754, 723, 81]] | 0      |

My solution to the ### problem

```java
class Solution {
    public int solution(int[][] arr) {
        int answer = 0;
        for(int i = 0; i < arr.length - 1; i++){
            for(int j = 0; j < arr.length; j++){
                if(arr[i][j] != arr[j][i]){
                    return answer;
                }
            }
        }
        answer = 1;
        return answer;
    }
}

```

#### Solution

int answer = 0; : Initialize the variable answer to store the resulting value.

for(int i = 0; i < arr.length - 1; i++) : Iterates over the two-dimensional array, checking only the top half relative to the main diagonal. (arr.length is the size of the array.)

for(int j = 0; j < arr.length; j++) : Checks for symmetry by comparing the elements for the current row i and column j with the elements for column i and row j.

if(arr[i][j] != arr[j][i]) : if the current element and the element at the symmetric position are different (if not symmetric):

Set answer to 0, and exit the function.

answer = 1;: if all elements are symmetric, set answer to 1.

return answer;: Return the result, the value of answer.
