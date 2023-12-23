---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_The_Lowest_Common_Denominator
title: Finding the Lowest Common Denominator (with.Java)
# title: Finding the Lowest Common Denominator (with.Java)
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
date: 2023-12-23 09:00:00 +0900
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

## In this post, we've been discussing the "find the smallest value" problem.

We're going to learn by solving coding test problems, reflecting on the problems we've solved, and exploring other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### The problem

The least common value is the value that occurs most often among a given set of values.

Complete the solution function so that, given an array of integers array as a parameter, it returns the least common value.

If there are multiple least common values, return -1.

#### Example input and output

| array                 | result |
| --------------------- | ------ |
| [1, 2, 3, 3, 3, 3, 4] | 3      |
| [1, 1, 2, 2, 2]       | -1     |
| [1 ]                  | 1      |

My solution to the ### problem

```java
import java.util.Map;
import java.util.HashMap;

class Solution {
    public int solution(int[] array) {
        Map<Integer, Integer> frequencyMap = new HashMap<>();
        for (int num : array) {
            frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);
        }

        int mode = -1;
        int maxFrequency = 0;

        for (Map.Entry<Integer, Integer> entry : frequencyMap.entrySet()) {
            int num = entry.getKey();
            int frequency = entry.getValue();

            if (frequency > maxFrequency) {
                mode = num;
                maxFrequency = frequency;
            }else if(frequency == maxFrequency){
                mode = -1;
            }
        }
    }
} return mode;
```

#### Solution

import java.util.Map;, import java.util.HashMap;: Add import statements to use the Map and HashMap classes.

public int solution(int[] array) : Declares the function solution, takes an array of integers array as input parameter. The function returns an integer value.

Map<Integer, Integer> frequencyMap = new HashMap<>();: Create a HashMap named frequencyMap that stores integer values and the frequency of those values. The map takes an integer as key and stores the frequency of that integer as value.

for (int num : array) : array Perform the following operations while iterating over each element of array

frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);: With the current element num as key, get the value of that key from frequencyMap, and use getOrDefault to update the frequency by setting 0 as the default and adding 1 if there is no value. This will record the frequency of each number appearing in the array in the map.

int mode = -1;, int maxFrequency = 0;: Initialize a variable to store the least frequent value (mode) and its frequency. initialize mode to -1, maxFrequency to 0.

for (Map.Entry<Integer, Integer> entry : frequencyMap.entrySet()) : Do the following, repeating for each entry in frequencyMap.

int num = entry.getKey();, int frequency = entry.getValue();: Get the key and value of the current entry, where num represents the number and frequency represents the frequency of that number.

if (frequency > maxFrequency) : If the frequency of the current number is greater than the maximum frequency, do the following operations.

mode = num;: Update the mode variable to the current number.

maxFrequency = frequency;: Update the maximum frequency to the current frequency.

else if (frequency == maxFrequency): If the frequency of the current number is equal to the maximum frequency, it indicates that a duplicate minimum value exists.

mode = -1;: Set the mode variable to -1 to indicate the presence of a duplicate minimum value.

return mode;: Returns the least common value (mode) as the return value of the function.
