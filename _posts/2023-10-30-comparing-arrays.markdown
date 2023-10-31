---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Comparing_Arrays
title: Comparing Arrays (with.Java)
# title: Comparing Arrays (with.Java)
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
date: 2023-10-30 09:00:00 +0900
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

### We've learned about comparing arrays.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

In this problem, we define the case relationship between two arrays of integers as follows.

If the two arrays are different lengths, the longer one is greater.

If the arrays are the same length, the sum of all the elements in each array is compared and the one that is larger is greater if they are different and equal if they are the same.

Given two integer arrays arr1 and arr2, write a solution function that returns -1 if arr2 is larger, 1 if arr1 is larger, and 0 if the two arrays are equal, for the case relationship of the arrays defined above.

##### Example input and output

| arr1             | arr2               | result |
| ---------------- | ------------------ | ------ |
| [49, 13]         | [70, 11, 2]        | -1     |
| [100, 17, 84, 1] | [55, 12, 65, 36]   | 1      |
| [1, 2, 3, 4, 5]  | [3, 3, 3, 3, 3, 3] | 0      |

#### My solution to the problem

```java
class Solution {
    public int[] solution(int[] arr) {
        int[] answer;
        int idx = 1;
        for(int i = 0; i < (int) Math.pow(2,10); i++){
            if(arr.length == (int) Math.pow(2,i)){
                idx = (int) Math.pow(2,i);
                break;
            } else{
                if(arr.length < (int) Math.pow(2,i)){
                    idx = (int) Math.pow(2,i);
                    break;
                }
            }
        }
        answer = new int[idx];
        for(int i = 0; i < answer.length; i++){
            if(arr.length - 1 < i){
                answer[i] = 0;
            }else{
                answer[i] = arr[i];
            }
        }
    } return answer;
}
```

##### Solution Explanation

First, compare the lengths of the two arrays arr1 and arr2. There are two cases: when they are the same length and when they are different.

If they are the same length, then we iterate over them and sum all the elements in each array.

The variable compare1 stores the sum of all the elements in arr1, and the variable compare2 stores the sum of all the elements in arr2.

We now compare the size of the two sums by comparing compare1 and compare2.

If compare1 is greater than compare2, store 1 in answer.

If compare1 is less than compare2, store -1 in answer.

If the two sums are equal, store 0 in answer.

If the lengths of the two arrays are different, it finds the one with the longer length and stores 1 or -1 in answer.

The code is a simple function that compares the two given arrays, considers their lengths and sums, and returns a result. The resulting value is stored in answer, which will be either 1, -1, or 0.
