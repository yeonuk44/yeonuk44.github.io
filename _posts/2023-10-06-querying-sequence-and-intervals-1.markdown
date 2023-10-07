---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Querying_Sequences_And_Intervals_1
title: Querying sequences and intervals 1 (with.Java)
# title: Querying sequences and intervals 1 (with.Java)

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
date: 2023-10-06 09:00:00 +0900
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

### We've been learning about sequences and interval queries.

We'll do this by solving coding test questions, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of integers, arr, and a two-dimensional array of integers, queries.

The elements of queries, each representing one query, are of the form [s, e].

For each query, add 1 to arr[i] for all i such that s ≤ i ≤ e, in order.

Complete the solution function to return arr after processing the queries according to the above rules.

##### Example input and output

| arr             | queries                | result             |
| --------------- | ---------------------- | ------------------ |
| [0, 1, 2, 3, 4] | [[0, 1],[1, 2],[2, 3]] | [1, 3, 4, 4, 4, 4] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int[] solution(int[] arr, int[][] queries) {
        int[] answer = arr;
        int idx = 0;
        for(int i = 0; i < queries.length; i++){
            for(int j = queries[i][0]; j <= queries[i][1]; j++){
                answer[j] += 1;
            }
        }
        } return answer;
    }
}
```

##### solution description

int[] answer = arr;: Initialize the resulting array answer to arr. This way, answer will point to the same array as arr.

for(int i = 0; i < queries.length; i++) : Iterate over the array queries, processing each query.

for(int j = queries[i][0]; j <= queries[i][1]; j++) : Iterate over the range for each query, incrementing the elements of the answer array within that range by 1.

return answer;: After processing all the queries, return the changed answer array.

This code does the job of incrementing the elements of arr by 1 that correspond to the ranges in the queries array.

But be careful, because the answer array references the arr array, this action also affects the arr array.

So if you want to store the result in a new array without changing the arr array, you need to create a new array and make changes to it.
