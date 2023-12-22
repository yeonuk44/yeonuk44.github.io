---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Array_Truncation
title: Array Truncation (with.Java)
# title: Array Truncation (with.Java)
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
date: 2023-12-22 09:00:00 +0900
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

## This is the "Truncate Array" problem.

We're going to learn by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

Given an array of integers numbers and integers num1 and num2 as parameters, complete the solution function so that it returns an array of integers truncated from the num1st index of numbers to the num2nd index of numbers.

#### Limitations

2 ≤ length of numbers ≤ 30

0 ≤ element of numbers ≤ 1,000

0 ≤num1 < num2 < length of numbers

#### Example input and output

| numbers         | num1 | num2 | result    |
| --------------- | ---- | ---- | --------- |
| [1, 2, 3, 4, 5] | 1    | 3    | [2 ,3, 4] |
| [1, 3, 5]       | 1    | 2    | [3, 5]    |

My solution to the ### problem

```java
import java.util.*;

class Solution {
    public int[] solution(int[] numbers, int num1, int num2) {
        int[] answer = Arrays.copyOfRange(numbers, num1, num2 + 1);
        return answer;
    }
}
```

#### Solution Explanation

There is no direct method for slicing an array in Java.

However, you can copy parts of an array to create a new array.

For example, you can slice an array using the Arrays.copyOfRange() method. The above problem was solved by using that method to slice and copy into a new array.

In the example above, Arrays.copyOfRange(numbers, num1, num2 + 1) creates a partial array of num1 through num2 from the array numbers. The reason for the +1 is to include num2 as well.
