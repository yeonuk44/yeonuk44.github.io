---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Creating_An_Array_3
title: Creating an Array 3 (with.Java)
# title: Creating an Array 3 (with.Java)

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
date: 2023-09-23 09:00:00 +0900
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

### About Creating Arrays 3 (with.Java)

We're going to take a look at solving a coding test problem, provide a retrospective on the problem we solved, and learn about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array arr of integers and an array intervals containing two intervals.

The intervals are always given in the order [[a1, b1], [a2, b2]] and each interval is a closed interval. A closed interval is one that contains both end values and the values in between.

Complete the solution function by concatenating the array corresponding to the first interval of the array arr and the array corresponding to the second interval to create a new array and return it.

##### Example input and output

| arr             | intervals        | result                   |
| --------------- | ---------------- | ------------------------ |
| [1, 2, 3, 4, 5] | [[1, 3], [0, 4]] | [2, 3, 4, 1, 2, 3, 4, 5] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int[] solution(int[] arr, int[][] intervals) {
        int[] answer;
        int[] temp1;
        int[] temp2;
        int a1 = intervals[0][0];
        int b1 = intervals[0][1];
        int a2 = intervals[1][0];
        int b2 = intervals[1][1];

        temp1 = new int[b1 - a1 + 1];
        for(int l = a1; l <= b1; l++) {
            temp1[l - a1] = arr[l];
        }

        temp2 = new int[b2 - a2 + 1];
        for(int l = a2; l <= b2; l++) {
            temp2[l - a2] = arr[l];
        }

        } answer = new int[temp1.length + temp2.length];
        for(int i = 0; i < temp1.length; i++) {
            answer[i] = temp1[i];
        }
        int e = 0;
        for(int i = temp1.length; i < answer.length; i++) {
            answer[i] = temp2[e++];
        }
        } return answer;
    }
}
```

##### Solution

int[] answer;, int[] temp1;, int[] temp2;: Declare an array answer and two temporary arrays temp1 and temp2 to store the result.

int a1 = intervals[0][0];, int b1 = intervals[0][1];, int a2 = intervals[1][0];, int b2 = intervals[1][1];: Extract the beginning and end of the first and second intervals from the given interval intervals.

temp1 = new int[b1 - a1 + 1];: Create a temp1 array that fits the size of the first interval.

for(int l = a1; l <= b1; l++) {: Iterate over the first interval, copying the elements of that interval into the temp1 array.

temp2 = new int[b2 - a2 + 1];: Create a temp2 array the size of the second interval.

for(int l = a2; l <= b2; l++) {: Iterate over the second interval, copying the elements of that interval into the temp2 array.

answer = new int[temp1.length + temp2.length];: Set the size of the resulting array answer to the sum of the sizes of the two temporary arrays.

Copy the elements of the first interval (temp1) to the front of the answer array.

Copy the elements of the second part (temp2) after the first part of the answer array.

return answer;: Returns the array answer, which finally combines the elements of the temp1 and temp2 sections.
