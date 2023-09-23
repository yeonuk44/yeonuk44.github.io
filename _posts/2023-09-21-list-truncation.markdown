---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_List_Truncation
title: List Truncation, how to truncate and assign to an array for a given integer and list (with.Java)
# title: List Truncation, how to truncate and assign to an array for a given integer and list (with.Java)

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
date: 2023-09-21 09:00:00 +0900
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

### About List Truncation (with.Java)

We're going to solve a coding test problem, reflect on the problem we solved, and learn about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given an integer n, a list slicer containing three integers, and a list num_list containing multiple integers, let's call the integers in slicer a, b, and c. We want to slice num_list according to n as follows.

n = 1 : index 0 through index b of num_list

n = 2 : index a to the last index in num_list

n = 3 : index a to index b in num_list

n = 4 : from index a in num_list to index b in num_list at interval c

Complete the solution function so that it returns a correctly sliced list.

##### Example input and output

n: 3

slicer: [1,5,2]

num_list: [1,2,3,4,5,6,7,8,9]

result: [2,3,4,5,6]

The list truncated from [1, 2, 3, 4, 5, 6, 7, 8, 9] from index 1 to index 5 is [2, 3, 4, 5, 6].

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int[] solution(int n, int[] slicer, int[] num_list) {
        int[] arr = {};
        int a = slicer[0], b = slicer[1], c = slicer[2];
        if(n == 1){
            arr = new int[b + 1];
            for(int i = 0; i <= b; i++) {
                arr[i] = num_list[i];
            }
        } else if(n == 2){
            arr = new int[num_list.length - a];
            for(int i = a; i < num_list.length; i++) {
                arr[i - a] = num_list[i];
            }
        } else if(n == 3){
            arr = new int[b - a + 1];
            for(int i = a; i <= b; i++) {
                arr[i - a] = num_list[i];
            }
        } else if(n == 4){
            arr = new int[(b - a) / c + 1];
            for(int i = a; i <= b; i += c) {
                arr[(i - a) / c] = num_list[i];
            }
        }
        } return arr;
    }
}
```

##### Solution

A, B, and C are used to take values from the slicer list in turn.

If n = 1:
Create a new array containing the first element of num_list to the bth element.

If n = 2:
Creates a new array containing the ath to the last element of num_list.

If n = 3:
Creates a new array containing the ath element of num_list through the bth element.

If n = 4:
Creates a new array containing from the ath element of num_list to the bth element, selecting elements at c intervals.

Result:
Returns the new array created based on the above conditions.

In other words, this code does the job of truncating num_list in different ways depending on n and slicer, and returns a new truncated array as the result.

There are other solutions out there, and I'll compare their pros and cons with my code.

###### Other solutions

```java
import java.util.*;
class Solution {
    public int[] solution(int n, int[] slicer, int[] num_list) {
        List<Integer> list = new ArrayList<>();
        int a = slicer[0];
        int b = slicer[1];
        int c = slicer[2];
        if(n == 1) {
            for(int i =0; i<b+1; i++) {
                list.add(num_list[i]);
            }
        }else if(n == 2) {
            for(int i = a; i<num_list.length; i++) {
                list.add(num_list[i]);
            }
        }else if(n ==3) {
            for(int i = a; i<b+1; i++) {
                list.add(num_list[i]);
            }
        }else if(n == 4) {
            for(int i = a; i<b+1; i+=c) {
                list.add(num_list[i]);

            }
        }
        } int[] answer = list.stream().mapToInt(x -> x).toArray();
        return answer;
    }
}
```

The newly presented code:
Pros:Flexibility: Because we use ArrayList, we don't have to specify the size of the array in advance, and we can add elements dynamically, making the code more concise and flexible.
Readability: easier to understand with fewer variables and clearer logic.
Cons: Efficiency: Because it uses ArrayList and stream operations, it can take a little more time and memory than using raw arrays.

Original code:
Pros:Efficiency: Uses raw arrays, so memory and time complexity can be lower.
Cons:Complexity: The code is a bit more complicated because you have to specify the size of the array up front. You have to calculate the size of the array separately for each case depending on n.

Conclusion.
The newly presented code has good points in terms of readability and flexibility, but for large datasets, the original code may be slightly more efficient.
