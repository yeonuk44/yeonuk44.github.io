---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Slice_An_Array
title: Slice an Array (with.Java)
# title: Slice an Array (with.Java)

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
date: 2023-09-25 09:00:00 +0900
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

### In this article, we learned how to slice an array, and how to determine and control the index siphoning of a given array by query value.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of integers, arr, and a query, query.

Repeat the following operations while traversing query.

At even indices, truncate and discard the trailing query[i] indices in arr, except for query[i].

For odd indices, truncate and discard the portion of arr before query[i], excluding query[i] from arr.

After doing the above, complete the solution function to return a partial array of the remaining arr.

##### Example input and output

arr: [0, 1, 2, 3, 4, 5]

query: [4,1,2]

result: [1, 2, 3]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr, int[] query) {
        for(int i = 0; i < query.length; i++) {
            if(i % 2 == 0) {
                arr = Arrays.copyOfRange(arr, 0, query[i] + 1);
            } else {
                arr = Arrays.copyOfRange(arr, query[i], arr.length);
            }
        }
        } return arr;
    }
}
```

##### solution Description

The solution function takes two integer arrays, arr and query, as input. arr is the target array to manipulate, and query contains the index information to perform the manipulation.

At the beginning of the function, loop the length of query and perform the following operations:

For even indices: When the loop variable i is even, remove all subsequent elements from arr, including the query[i]th index. For example, if arr = [0, 1, 2, 3, 4, 5] and query[i] is 2, the result is [0, 1, 2].

For odd indices: When i is odd, leave the query[i]th index to the end of arr, and remove all elements before it. For example, if arr = [0, 1, 2, 3, 4, 5] and query[i] is 2, the result would be [2, 3, 4, 5].

If you do this for every element in query, you'll end up with a partial array of the remaining arr.

Java's Arrays.copyOfRange method makes it easy to copy a specific range of an array, allowing you to perform the above operations efficiently.

###### See

If the array in arr has a fixed size and you use Arrays.copyOfRange, the elements will be reduced. \*\*Will the size of the array decrease as well?

The Arrays.copyOfRange method creates a new array by extracting a specified range of elements from the original array. Therefore, the size of the new array created will match the length of the specified range.

For example, calling Arrays.copyOfRange(arr, 0, 3) creates a new array by copying the elements from index 0 to index 2 of the original array arr. The size of the new array will therefore be 3.

In this way, Arrays.copyOfRange makes it easy to extract the elements of a desired range and create a new array sized to fit that range. So in this problem, the size of arr will continue to fluctuate based on the elements in the query.

Good luck.
