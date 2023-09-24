---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_A_Region_Of_2
title: How to find a region of 2 (with.Java)
# title: How to find a region of 2 (with.Java)

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
date: 2023-09-24 09:00:00 +0900
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

### How to find the area of 2 (with.Java)

We're going to go through a series of coding test problems, looking back at the problems we solved and learning about other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of integers, arr. Complete a solution function that returns the smallest contiguous subarray that contains all the 2s in arr.

However, if arr contains no 2s, return [-1].

##### Example input and output

arr: [1, 2, 1, 4, 5, 2, 9]

result: [2, 1, 4, 5, 2]

The only indices with a 2 are indices 1 and 5, so this returns a partial array of indices 1 through 5, [2, 1, 4, 5, 2].

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr) {
        int startIndex = -1;
        int endIndex = -1;

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == 2) {
                if (startIndex == -1) {
                    startIndex = i;
                }
                endIndex = i;
            }
        }

        if (startIndex == -1 || endIndex == -1) {
            return new int[]{-1};
        }

        int[] answer = new int[endIndex - startIndex + 1];
        for (int j = 0; j < answer.length; j++) {
            answer[j] = arr[startIndex + j];
        }

        } return answer;
    }
}
```

##### Explanation of the solution

Initializing variables: startIndex and endIndex are initialized to -1 each. These values indicate that '2' has not yet been found.

Find the location of '2': Traverse the given array arr to find the location of '2'.

startIndex stores the index of the first found '2'.

endIndex stores the index of the last '2' found.

This means that at the end of the iteration, startIndex and endIndex represent the location of the first '2' and the last '2' in the array.

Handling when no '2' is found: If either startIndex or endIndex is -1, it is assumed that no '2' is found and [-1] is returned.

Create a partial array: Create a partial array between startIndex and endIndex.

The length of the answer array is (endIndex - startIndex + 1), which means it will contain elements from startIndex to endIndex.

Each element in the partial array copies a value from the original array starting at startIndex and ending at endIndex.

Result: Returns the created partial array answer. This array contains all elements between the first '2' and the last '2' in arr.
