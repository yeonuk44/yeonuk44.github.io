---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Make_2_Dimensional
title: Making it two-dimensional (with.Java)
# title: Making it two-dimensional (with.Java)
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
date: 2024-02-06 09:00:00 +0900
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

## This is an article about the problem of “making it 2-dimensional.”

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The integer array num_list and the integer n are given as parameters.

Complete the solution function to return num_list by converting it to a two-dimensional array as described below.

Since num_list is [1, 2, 3, 4, 5, 6, 7, 8] with length 8 and n is 2, we change num_list to 2\*4 array as follows:

When changing to 2-dimensional, the elements of num_list are divided into n elements from the beginning and changed to a 2-dimensional array.

#### Restrictions

- The length of num_list is several times n.
- 0 ≤ length of num_list ≤ 150
- 2 ≤ n < length of num_list

#### Input/Output Example

| num_list                           | n   | result                                   |
| ---------------------------------- | --- | ---------------------------------------- |
| [1, 2, 3, 4, 5, 6, 7, 8]           | 2   | [[1, 2], [3, 4], [5, 6], [7, 8]]         |
| [100, 95, 2, 4, 5, 6, 18, 33, 948] | 3   | [[100, 95, 2], [4, 5, 6], [18, 33, 948]] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int[][] solution(int[] num_list, int n) {
         int[][] answer = new int[num_list.length / n][n];
         int temp = 0;
         for(int i = 0; i < num_list.length / n; i++){
             for(int j = 0; j < n; j++){
                 answer[i][j] = num_list[temp++];
             }
         }
         return answer;
     }
}
```

### Solution explanation

**Main Logic**

answer defines the size of the array as num_list.length / n rows and n columns.

Move the elements of a one-dimensional array into a two-dimensional array using a double loop.

**Function Description**

We used a method of initializing the array and assigning values directly without using a special function.

**Direction for improvement**

Depending on the input or situation, it may be a good idea to add an option to choose how to fill or ignore the last row.

Through exception handling, the code can be supplemented to ensure appropriate processing by checking the size of num_list and the condition of n.
