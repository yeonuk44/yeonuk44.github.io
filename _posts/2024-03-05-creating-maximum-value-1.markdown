---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Creating_Maximum_Value_1
title: Creating maximum value 1 (with.Java)
# title: Creating maximum value 1 (with.Java)
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
date: 2024-03-05 09:00:00 +0900
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

## This is an article about the "Creating the maximum value 1" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The integer array numbers is given as a parameter.

Complete the solution function to return the maximum value that can be created by multiplying two of the elements of numbers.

#### Restrictions

- 0 ≤ elements of numbers ≤ 10,000
- 2 ≤ length of numbers ≤ 100

#### Input/Output Example

| numbers               | result |
| --------------------- | ------ |
| [1, 2, 3, 4, 5]       | 20     |
| [0, 31, 24, 10, 1, 9] | 744    |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
import java.util.*;

class Solution {
     public int solution(int[] numbers) {
         int answer = 1;
         Arrays.sort(numbers);
         int endIdx = numbers.length - 1;
         for(int i = endIdx; i >= endIdx - 1; i--){
             answer *= numbers[i];
         }
         return answer;
     }
}
```

### Solution explanation

- Arrays.sort(numbers): Sorts an array.
- endIdx: Calculates the last index of the array.
- Use the for statement to select the two largest numbers and multiply them.

**Code Advantages**

- Use sorting: Sorting allows you to quickly select the largest number.
