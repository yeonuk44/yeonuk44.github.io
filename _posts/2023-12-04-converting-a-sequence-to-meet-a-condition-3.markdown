---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Converting_A_Sequence_To_Meet_A_Condition_3
title: Converting a sequence to meet a condition 3 (with.Java)
# title: Converting a sequence to meet a condition 3 (with.Java)
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
date: 2023-12-04 09:00:00 +0900
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

## This is a recap of the "Convert a sequence to match a condition 3" problem.

We're going to learn by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

Given an array of integers arr and a natural number k.

If k is odd, multiply every element in arr by k. If k is even, add k to every element in arr.

Complete a solution function that returns arr after these transformations.

#### Example input and output

| arr                    | k   | result                   |
| ---------------------- | --- | ------------------------ |
| [1, 2, 3, 100, 99, 98] | 3   | [3, 6, 9, 300, 297, 294] |
| [1, 2, 3, 100, 99, 98] | 2   | [3, 4, 5, 102, 101, 100] |

My solution to the ### problem

```java
class Solution {
    public int[] solution(int[] arr, int k) {
        if(k % 2 == 0){
            for(int i = 0; i < arr.length; i++){
                arr[i] += k;
            }
        }else{
            for(int i = 0; i < arr.length; i++){
                arr[i] = arr[i] * k;
            }
        }
        } return arr;
    }
}
```

#### Solution Explanation

if(k % 2 == 0) : if k is an even number:

Add k to each element of the array arr.

else : Otherwise (i.e., if k is odd):

Multiply each element of the array arr by k.

return arr;: Returns the changed array arr.

This code converts the elements of the array differently depending on whether k is odd or not.

If k is even, it adds k to each element; if k is odd, it multiplies each element by k and returns it.
