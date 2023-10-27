---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Power_Of_Two
title: Make the length of an array a power of two (with.Java)
# title: Make the length of an array a power of two (with.Java)
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
date: 2023-10-26 09:00:00 +0900
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

### In this article, we learned how to make the length of an array a power of two.

We'll do this by solving a coding test problem, reflecting on how we solved it, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

An array of integers, arr, is given as a parameter.

You want to add integer zeros after arr so that the length of arr is an integer power of 2.

Write a solution function that returns an array with the minimum number of zeros appended to arr.

##### Example input and output

| arr                | result                   |
| ------------------ | ------------------------ |
| [1, 2, 3, 4, 5, 6] | [1, 2, 3, 4, 5, 6, 0, 0] |
| [58, 172, 746, 89] | [58, 172, 746, 89]       |

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

##### Solution

int idx = 1;: Declare an integer variable named idx and set its initial value to 1. This variable will be used to determine the size of the new array.

for (int i = 0; i < (int) Math.pow(2, 10); i++) : Starts a for loop that sequentially examines values from 0 to 2^10 (1024). As the loop increments i, it compares it to the length of arr to find the appropriate array size.

if (arr.length == (int) Math.pow(2, i)) : If the power of 2 computed by the current value of i matches the length of arr, we have found the appropriate array size, so we set idx to that size and exit the loop.

else { if (arr.length < (int) Math.pow(2, i)) { idx = (int) Math.pow(2, i); break; } }: If the length of arr is less than the power of 2 computed by the current i, set idx to that size and exit the loop.

answer = new int[idx];: Create a new array answer with size idx.

Copy the contents of the array arr into the new array answer, but initialize the portion that exceeds the length of arr to zero.

Return the array answer.

The code above solves the problem, but it feels like it uses too many loops. Let's make the code more concise.

###### Improved code

```java
class Solution {
    public int[] solution(int[] arr) {
        int idx = 1;
        while (idx < arr.length) {
            idx *= 2;
        }

        int[] answer = new int[idx];
        for (int i = 0; i < arr.length; i++) {
            answer[i] = arr[i];
        }
    } return answer;
}
```

###### Improved code commentary

First code (using Math.pow):

This code uses a for loop to calculate powers of 2, and compares this value to the length of arr to find the appropriate array size. Each time the loop is executed, the Math.pow function is called to calculate the value of the power of two.
Second code (using a simple while loop):

The second code uses a simple while loop to calculate the value of a power of 2. It calculates the idx variable by starting with an initial value of 1 and multiplying it by 2 until it is less than the length of the arr.
The two codes provide functionally the same result, but the second code is more concise and efficient. The code is simpler because it uses a while loop to determine the size of the array without calling the Math.pow function. Also, the while loop is more efficient because it finds the size by repeatedly multiplying by 2 up to a certain array size.

Therefore, the second code is the more preferred approach and achieves the same result more efficiently.
