---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Average_Value_Of_Array
title: Average value of an array (with.Java)
# title: Average value of an array (with.Java)
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
date: 2024-01-08 09:00:00 +0900
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

## This is the "Average value of an array" problem.

We're going to learn about it by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### The problem

An array of integers, numbers, is given as a parameter.

Complete the solution function so that it returns the average value of the elements in numbers.

#### Example input and output

| numbers                                      | result |
| -------------------------------------------- | ------ |
| [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]              | 5.5    |
| [89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99] | 94.0   |

My solution to the ### problem

```java
class Solution {
    public double solution(int[] numbers) {
        double answer = 0;
        for(int num : numbers){
            answer += num;
        }
        answer /= numbers.length;
        return answer;
    }
}
```

#### Solution

double answer = 0;: initialize the variable answer to 0 to store the resulting value.

for (int num : numbers) : Iterate over each number (num) in the array numbers.

answer += num;: Compute the sum of all numbers by adding each number to answer.

answer /= numbers.length;: Calculate the average by dividing the sum of the numbers by the length of the array (the number of numbers).

return answer;: Returns the calculated average value.
