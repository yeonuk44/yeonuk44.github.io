---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Close_Number
title: Close number(with.Java)
# title: Close number(with.Java)
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
date: 2024-02-21 09:00:00 +0900
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

## This article examines the “close number” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When an integer array array and an integer n are given as parameters, complete the solution function so that it returns the number closest to n among the integers contained in the array.

#### Restrictions

- 1 ≤ length of array ≤ 100
- 1 ≤ element of array ≤ 100
- 1 ≤ n ≤ 100
- If there are multiple closest numbers, the smaller number is returned.

#### Input/Output Example

| s             | result |
| ------------- | ------ |
| "1 2 Z 3"     | 4      |
| "10 20 30 40" | 100    |
| "10 Z 20 Z 1" | 1      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
import java.util.*;
class Solution {
     public int solution(int[] array, int n) {
         int answer = 0;
         int temp = 101;
         Arrays.sort(array);
         for(int i = 0; i < array.length; i++){
             if(temp > Math.abs(n - array[i])){
                 answer = array[i];
                 temp = Math.abs(n - array[i]);
             }
         }
         return answer;
     }
}
```

### Solution explanation

- Initial value setting: Initialize the temp variable to 101. This value is set to be greater than the maximum difference of array elements.
- Sorting an array: Use the Arrays.sort method to sort an array in ascending order.
- Array traversal: Calculate the difference between each element and n while traversing the sorted array.
- Find the closest element: If a difference smaller than the minimum difference so far appears, the element is assigned to the answer and the temp value is updated.
- Return result: Returns the closest element if found.

**Code Advantages**

- Utilize ascending sort: You can use a sorted array to efficiently find the element closest to n.
- Concise Logic: Simple yet effective logic to find the closest array element.

**Code Disadvantages**

- Fixed initial value: The initial value 101 is determined by the maximum difference between array elements. If the values in the array are out of range, you must adjust these values appropriately.
- No handling when the array is empty: The current code does not take into account handling when the array is empty. I would recommend adding handling for empty arrays.
- No handling when there are multiple minimum differences: The current code does not handle cases where there are multiple minimum differences. For example, if the array is [1, 5, 9] and n is 6, both 5 and 9 have the minimum difference. I would recommend adding handling for this.
