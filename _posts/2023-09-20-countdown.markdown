---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Countdown
title: Countdown (with.Java)
# title: Countdown (with.Java)

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
date: 2023-09-20 09:00:00 +0900
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

### In this article, About Countdown (with.Java)

We're going to take a look at solving a coding test problem, provide a retrospective on the problem we solved, and explore other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given integers start_num and end_num, complete the solution function so that it returns a list of numbers decrementing by 1 from start_num to end_num.

##### Example input and output

| start_num | end_num | result                    |
| --------- | ------- | ------------------------- |
| 10        | 3       | [10, 9, 8, 7, 6, 5, 4, 3] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
import java.util.ArrayList;
import java.util.List;

public class Solution {
    public static void main(String[] args) {
        int start_num = 10;
        int end_num = 5;
        List<Integer> result = solution(start_num, end_num);
        System.out.println(result);
    }

    } public static List<Integer> solution(int start_num, int end_num) {
        List<Integer> result = new ArrayList<>();

        for (int i = start_num; i >= end_num; i--) {
            result.add(i);
        }

        } return result;
    }
}

```

##### Solution

int start_num = 10; and int end_num = 5;: initialize the starting number start_num to 10 and the ending number end_num to 5.

List<Integer> result = solution(start_num, end_num);: Call the solution function to store the numbers from the start number to the end number in a list, and assign them to the result variable.

System.out.println(result);: Print out the numbers stored in the list.

public static List<Integer> solution(int start_num, int end_num) : The solution function takes as input the starting number start_num and the ending number end_num, and returns a list containing the numbers from the starting number to the ending number.

List<Integer> result = new ArrayList<>(); : Create an integer list result to store the result.

for (int i = start_num; i >= end_num; i--) : Executes a decrementing iteration from the start number to the end number.

result.add(i);: Add each number i to the list result.

return result;: Returns the list result, which contains the numbers from the start number to the end number.

This code stores the numbers from the start number to the end number in a list in reverse order, and outputs the list.
