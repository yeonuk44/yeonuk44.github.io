---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Best_Set
title: The best set (with.Java)
# title: The best set (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, greedy]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-21 09:00:00 +0900
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

## We've learned about the best set (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Out of a redundant set of n natural numbers (collectively referred to as "set" for convenience), the set that satisfies the following two conditions is called the best set.

a set of numbers whose sum of each element is S

A set whose product of each element is maximized while satisfying the above conditions

For example, of a set of two natural numbers, there are four sets that add up to 9.

{ 1, 8 }, { 2, 7 }, { 3, 6 }, { 4, 5 }

Among them, {4, 5}, where the product of each element is the maximum, is the best set.

Given the number of elements in a set n and the sum s of all elements as parameters, complete the solution function that returns the best set.

#### Restrictions

- Please return the best set to a one-dimensional array (list, vector) arranged in ascending order.
- If the best set does not exist, return a one-dimensional array (list, vector) of size 1 by filling it with -1.
- The number of natural numbers n is a natural number greater than 1 and less than 10,000.
- The sum s of all the elements is a natural number greater than 1 and less than 100,000,000.

#### Input/output Examples

| n   | s   | result |
| --- | --- | ------ |
| 2   | 9   | [4, 5] |
| 2   | 1   | [-1]   |
| 2   | 8   | [4, 4] |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### problem solving

```java
import java.util.HashSet;
import java.util.ArrayList;
import java.util.Collections;

class Solution {
    ;
    public int[] solution(int n, int s) {
        int[] answer = new int[n];
        if(n > s){
            answer = new int[]{-1};
            return answer;
        }
        for(int i = 0; i < answer.length; i++){
            answer[i] = s / n;
        }
        int temp = s % n;
        for(int i = answer.length - 1; i >= 0; i--){
            if(temp == 0){
                break;
            }
            answer[i] += 1;
            temp--;
        }

        return answer;
    }
}
```

#### Solution Description

It solves the problem of creating an array of n elements with the given natural numbers n and s, but maximizing the product of the elements in the array.

To do this, the code follows the following procedure.

First, in order to divide each element in the array as evenly as possible, store the share of s divided by n in the array answer.

This is to maximize the product of the array by ensuring that each element has a larger value on average.

If n is greater than s, this means that s cannot be divided into n elements, so it returns an array with -1 elements.

After that, calculate the remainder of s divided by n, and add the remainder one by one from the back of the array.

By doing this, we adjust the sum of the array to be s, but also ensure that the elements of the array are distributed as evenly as possible.

This ensures that the product of the array is maximized.

The first iteration of the code initializes all elements of the array answer to s / n.

The second iteration uses the remaining temp values to add one by one from the back of the array.

By doing so, the elements of the array are kept as even as possible, and the product of the elements of the array is maximized.

##### Conclusion

This code solves the problem simply and efficiently, maximizing the product of an array by ensuring that the elements of the array are distributed as evenly as possible.
