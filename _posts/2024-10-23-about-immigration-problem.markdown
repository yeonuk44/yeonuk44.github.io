---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Immigration_Problem
title: Immigration Problem(with.Java)
# title: Immigration Problem(with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, binary search]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-23 09:00:00 +0900
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

## This is an article about immigration (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

N people are waiting in line for immigration.

Each examiner at each immigration desk takes different time to examine.

At first, all the examination tables are empty.

Only one judge can be judged at the same time.

The person standing at the front can go to the empty screening table for a screening.

However, if there is a screening table that finishes faster, you can wait and go there for a screening.

I want to minimize the time it takes for everyone to be judged.

Number of people waiting for immigration, when given as parameters the array times that each examiner takes to examine one person, write a solution function to return the minimum amount of time it takes for everyone to be screened.

#### Restrictions

- There are more than one person and no more than 1,000,000 people waiting for immigration.
- Each examiner takes more than one minute and no more than 1,000,000 minutes.
- The number of examiners is not less than one but not more than 100,000.

#### Input/output Examples

| n   | times  | return |
| --- | ------ | ------ |
| 6   | [7,10] | 28     |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### problem solving

```java
import java.util.Arrays;

class Solution {
    public long solution(int n, int[] times) {
        long answer = 0;
        Arrays.sort(times);
        long left = 0;
        long right = times[times.length - 1] * (long)n;

        while(left <= right){
            long mid = (left + right) / 2;
            long test_num = 0;
            for(int i = 0; i < times.length; i++){
                test_num += mid / times[i];
            }
            if(test_num < n){
                left = mid + 1;
            }else{
                answer = mid;
                right = mid - 1;
            }
        }
        return answer;
    }
}
```

#### Solution Description

Solve the problem of finding the minimum time for a given examiner to examine n persons in a given time.

For this, we use a binary search algorithm.

First, sort the times, the given time array, in ascending order.

This is a necessary step to set the minimum time and maximum time.

The left variable is then set to 0, and the right variable is set to be the time of the examiner (the last element in the times array) multiplied by n.

This is based on the assumption that the screening time takes up to the maximum.

While performing a binary search, set the mid value to an intermediate value between left and right.

mid is considered the current average time, and calculates how many people each examiner can judge within this time.

To do this, use the test_num variable to find the total number of people that all examiners can examine during mid time.

The test_num value is calculated by adding all the values of mid divided by each examiner's review time.

Afterwards, if test_num is less than n, this means that not everyone can be judged within the current time (mid), so set the left to mid + 1 to allocate more time.

Conversely, if test_num is n or higher, this means that everyone can be judged within the current time (mid), so set answer to mid and right to mid-1 to see if it is possible to allocate less time.

Repeat this process until the left is greater than right.

Finally, answer stores a minimum amount of time for everyone to be judged.

The algorithm uses binary exploration to reduce time complexity and solve problems efficiently.
