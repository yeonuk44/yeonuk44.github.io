---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Draw_K_Numbers_Random
title: Draw K numbers at random (with.Java)
# title: Draw K numbers at random (with.Java)
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
date: 2023-10-29 09:00:00 +0900
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

### In this article, we've been learning about randomly drawing K numbers.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

#### Problem

You want to create an array of k randomly selected numbers, but you can't think of a good way to do it, so you decide to randomize the numbers within a certain range and add them to the end of the array if they've never been seen before.

Assuming we already know what numbers will be randomized, let's estimate the actual array of length k that will be created.

You are given an array of integers, arr. Given that the random numbers in the problem will be given in the order they are stored in arr, complete a solution function that returns the resulting array.

However, if the length of the resulting array is less than k, return all the remaining values as -1.

##### Example input and output

| arr                | k   | result         |
| ------------------ | --- | -------------- |
| [0, 1, 1, 2, 2, 3] | 3   | [0, 1, 2]      |
| [0, 1, 1, 1, 1, 1] | 4   | [0, 1, -1, -1] |

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr, int k) {
        ArrayList<Integer> list = new ArrayList<>();
        int[] answer = new int[k];
        for(int i = 0; i < arr.length; i++){
            if(!list.contains(arr[i])){
                list.add(arr[i]);
            }
            if(list.size() == k){
                break;
            }
        }
        while (list.size() < k) {
            list.add(-1);
        }
        for(int i = 0; i < k; i++){
            answer[i] = list.get(i);
        }
        } return answer;
    }
}
```

##### Solution

ArrayList<Integer> list = new ArrayList<>();: Creates an ArrayList that stores elements of type Integer. This list will be used to remove duplicates and store the result.

int[] answer = new int[k];: Create an array answer to store the result. It is initialized to the size of k.

for(int i = 0; i < arr.length; i++): Starts a loop that iterates over the input array arr, removing duplicates and adding them to list.

if(!list.contains(arr[i])): If list does not contain arr[i] (i.e., it is not a duplicate),

list.add(arr[i]);: adds arr[i] to list.

if(list.size() == k): Terminate the iteration if the size of list is equal to k. In other words, no more duplicates are removed once the desired result size is reached.

while (list.size() < k): If the size of list is less than k,

list.add(-1);: Add -1 to list so that it reaches a size of k.

for(int i = 0; i < k; i++): Start a loop that copies the elements of list into the array answer.

answer[i] = list.get(i);: copy the i-th element of list to the i-th position in answer.

return answer;: Returns the final result, the array answer.

The code removes duplicate values, fills in -1 as needed, and creates and returns the resulting array. The size of the resulting array is equal to or less than k, and it contains only one duplicate value.
