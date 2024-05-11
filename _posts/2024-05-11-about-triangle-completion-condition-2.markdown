---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Triangle_Completion_Condition_2
title: Triangle completion condition 2 (with.Java)
# title: Triangle completion condition 2 (with.Java)
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
date: 2024-05-11 09:00:00 +0900
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

## This is an article about the "Triangle Completion Condition 2 (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

To create a triangle with three line segments, the following conditions must be met.

The length of the longest side must be less than the sum of the lengths of the other two sides.

The array sides containing the lengths of the two sides of the triangle is given as a parameter.

Complete the solution function so that it returns the number of integers that can be the remaining side.

#### Restrictions

- The elements of sides are natural numbers.
- The length of sides is 2.
- 1 ≤ elements of sides ≤ 1,000

#### Input/Output Example

<!-- | keyinput | board | result |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1] |
| ["down", "down", "down", "down", "down"] | [7, 9] | [0, -4] | -->

| sides   | result |
| ------- | ------ |
| [1, 2]  | 1      |
| [3, 6]  | 5      |
| [11, 7] | 13     |

### My solution to the problem

```java
import java.util.*;

class Solution {
     public int solution(int[] sides) {
         int answer = 0;
         Arrays.sort(sides);

         for(int i = (sides[1] - sides[0]) + 1; i <= sides[1]; i++){
             answer++;
         }
         for(int i = sides[1] + 1; i < sides[0] + sides[1]; i++){
             answer++;
         }

         return answer;
     }
}

```

### Solution explanation

Sorts the given array in ascending order.

This makes the first element of the array the smallest value and the second element the larger value.

In the first for loop, it repeats from the difference between the second element and the first element plus 1 to the second element and increments the answer value.

This is intended to include all values between the second and first elements.

For example, if the sides array is given as [3, 7], the first for loop iterates from 4 to 7 and increments the answer value 4 times.

The second for loop iterates from the value greater than the second element to the value less than the sum of the first and second elements and increments the answer value.

This is intended to include all values that are greater than the second element and less than the sum of the first and second elements. For example, if the sides array is given as [3, 7], the second for loop iterates from 8 to 9 and increments the answer value twice.

Returns the final calculated answer value.

The pros and cons of this code are:

- Pros: The code is concise and intuitive. Since the purpose is to calculate the answer value from a given array according to specific rules, it was implemented using simple loop and conditional statements. Because the calculation is performed after sorting the array, it can be useful for other calculations using sorted arrays.
- Disadvantage: Since there is no explanation of the given rule in the given code, it is difficult to understand what rule is followed just by the code. Therefore, additional information is needed. The variable names used in the code are unclear, which may reduce readability. Naming variables more meaningfully can make the code easier to understand.
