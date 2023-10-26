---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Empty_Array
title: Adding to and deleting from an empty array (with.Java)
# title: Adding to and deleting from an empty array (with.Java)
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
date: 2023-10-25 09:00:00 +0900
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

### In this article, we learned how to add and delete to an empty array.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

#### Problem

We have an empty array X that doesn't contain any elements.

Given an integer array arr and a boolean array flag of the same length as parameters, write a solution function that iterates over flag and, if flag[i] is true, adds arr[i] to the end of X arr[i] × 2 times; if flag[i] is false, removes the last arr[i] elements from X, and returns X. The solution function should return X.

##### Example input and output

| arr             | flag                              | result                         |
| --------------- | --------------------------------- | ------------------------------ |
| [3, 2, 4, 1, 3] | [true, false, true, false, false] | [3, 3, 3, 3, 3, 4, 4, 4, 4, 4] |

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr, boolean[] flag) {
        ArrayList<Integer> answer = new ArrayList<>();
        for(int i = 0; i < flag.length; i++){
            if(flag[i]){
                for(int j = 0; j < arr[i] * 2; j++){
                    answer.add(arr[i]);
                }
            } else{
                for(int j = 0; j < arr[i]; j++){
                    answer.remove(answer.size() - 1);
                }
            }
        }
        int[] result = new int[answer.size()];
        for(int i = 0; i < answer.size(); i++){
            result[i] = answer.get(i);
        }
    } return result;
}
```

##### Solution

ArrayList<Integer> answer = new ArrayList<>();: Create a list of integer arrays named answer. This list will be used to store the final result.

for(int i = 0; i < flag.length; i++) : Starts a loop with the length of the flag array.

if(flag[i]) : If flag[i] is true, perform the next action. This is the part that handles the case where it is true.

for(int j = 0; j < arr[i] _ 2; j++) : Loops twice as long as arr[i]. This part adds the value of arr[i] to the answer list twice as many times as the current value of arr[i]. For example, if arr[i] is 3, it adds 3 to the answer list by 3 _ 2 = 6.

else : If flag[i] is false, do the following. This is the part that handles the case of false.

for(int j = 0; j < arr[i]; j++) : Repeat as many times as arr[i]. This part removes elements from the answer list by the current value of arr[i]. We use the remove method to remove elements one by one from the back.

int[] result = new int[answer.size()];: Create an array of int result that fits the size of the answer list.

for(int i = 0; i < answer.size(); i++) : Iterate over all the elements in the answer list and copy them to the result array.

Finally, return the result array.

This code is a function that manipulates the values in the arr array based on the values in the flag array, stores the results in the answer list, and finally converts them to the result array and returns them.
