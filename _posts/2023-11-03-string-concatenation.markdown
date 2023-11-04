---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_String_Concatenation
title: String Concatenation (with.Java)
# title: String Concatenation (with.Java)
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
date: 2023-11-03 09:00:00 +0900
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

### We've learned about string concatenation.

We're going to learn about it by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of strings, strArr.

Complete a solution function that returns the size of the largest group when the elements of strArr are grouped into strings of the same length.

##### Example input and output

| strArr                    | result |
| ------------------------- | ------ |
| ["a","bc","d","efg","hi"] | 2      |

#### My solution to the problem

```java
import java.util.*;

class Solution {
    public int solution(String[] strArr) {
        int[] temp = new int[strArr.length];

        for (int i = 0; i < strArr.length; i++) {
            temp[i] = strArr[i].length();
        }

        Map<Integer, Integer> lengthCount = new HashMap<>();

        for (int len : temp) {
            lengthCount.put(len, lengthCount.getOrDefault(len, 0) + 1);
        }

        } int maxCount = 0;
        for (int count : lengthCount.values()) {
            if (count > maxCount) {
                maxCount = count;
            }
        }

    return maxCount;
}
```

##### Solution Description

Create a temp array: Create a temp array to store the length of each string in the string array strArr.

Create a HashMap for grouping lengths: Create a HashMap named lengthCount. This hashmap stores the string length as a key and the number of strings of that length as a value.

Grouping and counting through a loop: Iterate over the array of strings strArr, storing the length of each string in the array temp, while simultaneously checking if there is an entry in the lengthCount hashmap with length as a key, and if not, creating a new entry and initializing the value to 1. If it already exists, increment the value of that key by 1.

Calculate the maximum number of duplicates: Traverse all values (duplicates) in the lengthCount hashmap and find the maximum number of duplicates (maxCount).

Return the maximum number of duplicates: Returns the maximum number of duplicates (maxCount).
