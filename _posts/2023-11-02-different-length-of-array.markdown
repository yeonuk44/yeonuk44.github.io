---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Different_Length_Of_Array
title: Performing different operations on the length of an array (with.Java)
# title: Performing different operations on the length of an array (with.Java)
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
date: 2023-11-02 09:00:00 +0900
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

### In this article, we learned about different operations based on the length of an array.

We'll do this by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

An array of integers arr and an integer n are given as parameters.

Write a solution function that returns an array of all even-indexed positions in arr plus n if the length of arr is odd, or an array of all odd-indexed positions in arr plus n if the length of arr is even.

##### Example input and output

| arr                    | n   | result                 |
| ---------------------- | --- | ---------------------- |
| [49, 12, 100, 276, 33] | 27  | [76, 12, 127, 276, 60] |
| [444, 555, 666, 777]   | 100 | [444, 655, 666, 877]   |

#### My solution to the problem

```java
class Solution {
    public int[] solution(int[] arr, int n) {
        if(arr.length % 2 != 0){
            for(int i = 0; i < arr.length; i++){
                if(i % 2 == 0){
                    arr[i] += n;
                }
            }
        } else {
            for(int i = 0; i < arr.length; i++){
                if(i % 2 != 0){
                    arr[i] += n;
                }
            }
        }
        } return arr;
    }
}
```

##### Solution Explained

First, check whether the length of the array arr is odd or even.

Check if the length is odd with the condition arr.length % 2 != 0, and if it is even, execute the else block.

If the length is **odd**:

Use a for loop to traverse the array arr. The i variable represents the index in the array.

The if(i % 2 == 0) condition checks to see if the current index i is an even position. If it is an even position, it adds the value of n to that element.

If the length is **even**:

In this case, we enter the else block, which traverses the array arr.

The if(i % 2 != 0) condition checks to see if the current index i is in an odd position. If it is an odd position, it adds the value of n to that element.

Return the changed array arr.

This function performs a simple operation that adds n to the elements in odd or even positions of the given array arr.

The distinction between elements in odd and even positions is based on whether the array is odd or even in length, and the operation is performed accordingly.
