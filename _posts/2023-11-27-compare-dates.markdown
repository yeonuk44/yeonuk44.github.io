---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Compare_Dates
title: Compare Dates (with.Java)
# title: Compare Dates (with.Java)
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
date: 2023-11-27 09:00:00 +0900
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

## This is the "Compare Dates" problem.

We're going to learn by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

You are given two integer arrays date1 and date2.

Each of the two arrays represents a date and is given in the form [year, month, day], where year represents the year, month represents the month, and day represents the day.

Complete the solution function to return 1 if date1 is earlier than date2, or 0 otherwise.

#### Example input and output

| date1          | date2          | result |
| -------------- | -------------- | ------ |
| [2021, 12, 28] | [2021, 12, 29] | 1      |
| [1024, 10, 24] | [1024, 10, 24] | 0      |

My solution to the ### problem

```java
class Solution {
    public int solution(int[] date1, int[] date2) {
        int answer = 0;
        for(int i = 2; i >= 0; i--){
            if(date1[i] < date2[i]){
                answer = 1;
            }else if(date1[i] > date2[i]){
                answer = 0;
            }
        }
    } return answer;
}
```

#### solution description

int answer = 0;: Initialize an integer variable, answer, to store the result. The initial value is 0.

for(int i = 2; i >= 0; i--) : Compares each date field (year, month, day) using a loop starting at 2 and iterating down to 0. The loop starts with the year and compares in the following order: year, month, day.

if(date1[i] < date2[i]): If the value of date1 is less than the value of date2 in the current field:

Set answer to 1. This indicates when date1 is earlier than date2
.
else if(date1[i] > date2[i]) : If the value of date1 is greater than the value of date2 in the current field:

Set answer to 0. This indicates when date1 is later than date2.

return answer;: Returns the value of answer, which represents the result of comparing the dates.
