---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Doubling_An_Array
title: Doubling an Array (with.Java)
# title: Doubling an Array (with.Java)
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
date: 2023-12-20 09:00:00 +0900
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

## This is the "Doubling an Array" problem.

We're going to learn by solving coding test questions, looking back at the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### The problem

An array of integers, numbers, is given as a parameter.

Complete the solution function so that it returns an array with twice as many elements as each element in numbers.

#### Example input and output

| numbers                   | result                     |
| ------------------------- | -------------------------- |
| [1, 2, 3, 4, 5]           | [2, 4, 6, 8, 10]           |
| [1, 2, 100, -99, 1, 2, 3] | [2, 4, 200, -198, 2, 4, 6] |

My solution to the ### problem

```java
class Solution {
    public int[] solution(int[] numbers) {
        for(int i = 0; i < numbers.length; i++){
            numbers[i] *= 2;
        }
    } return numbers;
}
```

#### solution description

public int[] solution(int[] numbers) : Declares a function solution and takes an integer array numbers as an input parameter. The function returns an array of integers.

for(int i = 0; i < numbers.length; i++){: Starts a loop to access each element of the array numbers. The variable i represents the index in the array through the iteration.

numbers[i] \*= 2;: Doubles the array element corresponding to the current index i. This code modifies the value of the current array element by multiplying it by 2.

}: Marks the end of the loop. It exits after all elements of the array have been processed.

return numbers;: Returns the modified array numbers as the return value of the function. So, this function doubles all the elements of the given array and returns the result.
