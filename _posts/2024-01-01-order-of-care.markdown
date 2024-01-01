---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Order_Of_Care
title: Order of Care (with.Java)
# title: Order of Care (with.Java)
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
date: 2024-01-01 09:00:00 +0900
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

## This is the "Order of Care" problem.

We're going to learn by solving coding test problems, reflecting on the problems we've solved, and exploring other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### Problem

Dr. Murmur, a surgeon, wants to order patients in the emergency room based on their urgency.

Given an integer array emergency as a parameter, complete the solution function so that it returns an array that orders the appointments in order of increasing urgency.

#### Limitations

No duplicate elements.

Length of 1 ≤ emergency ≤ 10

Elements in 1 ≤ emergency ≤ 100

#### Example input and output

| emergency             | result                |
| --------------------- | --------------------- |
| [3, 76, 24]           | [3, 1, 2]             |
| [1, 2, 3, 4, 5, 6, 7] | [7, 6, 5, 4, 3, 2, 1] |
| [30, 10, 23, 6, 100]  | [2, 4, 3, 5, 1]       |

My solution to the ### problem

```java
import java.util.*;

class Solution {
    public int[] solution(int[] emergency) {
        int[] answer = new int[emergency.length];
        Arrays.fill(answer, 1);

        for(int value : emergency){
            for(int i = 0; i < emergency.length; i++){
                if(value > emergency[i]){
                    answer[i]++;
                }
            }
        }
    } return answer;
}
```

#### Solution explanation

Solution: Function to calculate the priority for an emergency.

Input: emergency - an array of integers representing emergencies.

Output: an array of integers representing the priority for the emergency.

Functions used:

Arrays.fill(answer, 1);: The fill method of the Arrays class is used to fill an array with a specific value.

In this case, it initializes the answer array to 1.

What could be improved:

Improve performance: The current code uses a double loop to calculate the priority for each emergency.

This can impact performance as the number of emergencies increases.

You may want to consider a different algorithm to improve performance.

Modularize your code: Your current code is all implemented in one function.

You can consider modularizing the code by breaking the function into smaller pieces.

For example, you could break out the part that calculates the priority into a separate function.

Utilize a data structure: You can improve performance by changing the way you calculate prioritization for emergencies to an efficient data structure.

For example, using a Heap data structure allows for more efficient prioritization calculations.

Consider these improvements to make your code more efficient.
