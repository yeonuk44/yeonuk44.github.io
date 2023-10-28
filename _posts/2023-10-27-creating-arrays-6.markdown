---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Creating_Arrays_6
title: Creating Arrays 6 (with.Java)
# title: Creating Arrays 6 (with.Java)
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
date: 2023-10-27 09:00:00 +0900
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

### This is the end of the article on Creating Arrays 6.

We're going to learn about it by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of integers, arr, consisting of only 0s and 1s. You want to create a new array, stk, from arr.

Set the initial value of i to 0, and if i is less than the length of arr, repeat the following.

If stk is an empty array, then add arr[i] to stk and add 1 to i.

If stk has elements, and the last element in stk is equal to arr[i], remove the last element in stk from stk and add 1 to i.

If there are elements in the stk and the last element in the stk is different from arr[i], add arr[i] to the very end of the stk and add 1 to i.

Complete the solution function to return the stk created after doing the above.

However, if you need to return an empty array, return [-1].

##### Example input and output

| arr                | result          |
| ------------------ | --------------- | --------------- |
| [0, 1, 1, 1, 1, 0] | [0, 1, 0]       |
| [0, 1, 0, 1, 0]    | [0, 1, 0, 1, 0] | [0, 1, 0, 1, 0] |
| [0, 1, 1, 0, 0]    | [-1]            |

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr) {
        int[] answer;
        ArrayList<Integer> stk = new ArrayList<>();
        for(int i = 0; i < arr.length; i++){
            if(stk.isEmpty()){
                stk.add(arr[i]);
            } else if(stk.get(stk.size() - 1) != arr[i]){
                stk.add(arr[i]);
            } else {
                stk.remove(stk.size() - 1);
            }
        }
        if(stk.isEmpty()){
            answer = new int[1];
            answer[0] = -1;
        }else {
            answer = new int[stk.size()];
            for(int i = 0; i < stk.size(); i++){
                answer[i] = stk.get(i);
            }
        }

    } return answer;
}
```

##### Solution

int[] answer;: Declare the result array.

ArrayList<Integer> stk = new ArrayList<>();: Create an integer ArrayList named stk. This ArrayList will serve as temporary storage for removing duplicate elements.

for(int i = 0; i < arr.length; i++): Traverse the given array arr.

if(stk.isEmpty()): If stk is empty, add the current array element.

stk.add(arr[i]);: add the current array element arr[i] to stk.
else if(stk.get(stk.size() - 1) != arr[i]): if stk is not empty, and the current array element is different from the last element in stk, add the current array element. This is a condition for removing duplicates.

stk.add(arr[i]);: Add the current array element arr[i] to stk.
else: If stk is not empty, and the current array element is the same as the last element in stk, remove the last element in stk because it is a duplicate.

stk.remove(stk.size() - 1);: Remove the last element of stk.
if(stk.isEmpty()): If stk is empty, it is treated as not having duplicate elements.

answer = new int[1];: Initialize the resulting array to size 1.

answer[0] = -1;: Set the only element of the resulting array to -1.

Otherwise, the element remaining in stk is the non-duplicate element. Copy it to the answer array.

answer = new int[stk.size()];: Initialize the resulting array to the same size as stk.

Copy the elements of stk into answer, using a loop for array copying.

Finally, return the answer array.
