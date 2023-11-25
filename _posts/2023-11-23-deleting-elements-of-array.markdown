---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Deleting_Elements_Of_Array
title: Deleting Elements of an Array (with.Java)
# title: Deleting Elements of an Array (with.Java)
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
date: 2023-11-23 09:00:00 +0900
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

## This is a recap of the "Delete elements of an array" problem.

We're going to learn by solving the coding test problem, reflecting on how we solved it, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

We have an array of integers, arr and delete_list.

Write a solution function that deletes all of the elements in delete_list from arr and returns an array with the remaining elements in the same order as they were in arr.

#### Example input and output

| arr                       | delete_list                 | result                 |
| ------------------------- | --------------------------- | ---------------------- |
| [293, 1000, 395, 678, 94] | [94, 777, 104, 1000, 1, 12] | [293, 395, 678]        |
| [110, 66, 439, 785, 1]    | [377, 823, 119, 43]         | [110, 66, 439, 785, 1] |

### My solution to the problem

```java
import java.util.ArrayList;
class Solution {
    public int[] solution(int[] arr, int[] delete_list) {
        ArrayList<Integer> arrList = new ArrayList<Integer>();
        int count = 0;
        for(int ele1: arr){
            for(int ele2: delete_list){
                if(ele1 == ele2){
                    count++;
                }
            }
            if(count == 0){
                arrList.add(ele1);
            }
            } count = 0;

        int[] answer = new int[arrList.size()];

        for(int i = 0; i < arrList.size(); i++){
            answer[i] = arrList.get(i);
        }
        return answer;
    }
}
```

#### Solution

ArrayList<Integer> arrList = new ArrayList<Integer>();: Creates an ArrayList arrList to store the integers. This list will be used to store all the elements except the ones to be deleted.

int count = 0;: Initialize the variable count, which will store the number of elements that match the element to be deleted.

for(int ele1 : arr) : Iterates over the input array arr, examining each element.

for(int ele2 : delete_list) : Iterate over the list to delete, delete_list, examining each element.

if(ele1 == ele2) : If the current ele1 and ele2 match:

Increment count.
if(count == 0) : If count is 0 (i.e., ele1 is not in delete_list):

Add ele1 to arrList.
count = 0;: initialize count to prepare for examining the next ele1 element.

int[] answer = new int[arrList.size()];: Create an array answer with size equal to the size of arrList.

for(int i = 0; i < arrList.size(); i++) : copy the elements of arrList into the array answer.

return answer;: Returns an array answer consisting of the elements not included in the list delete_list to be deleted.

This code collects the elements not included in the list to delete delete_list from the input array arr, creates a new array with them, and returns it.
