---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Length_Operations
title: 길이에 따른 연산(with.Java)
# title: Length-based operations (with.Java)

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
date: 2023-10-04 09:00:00 +0900
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

### In this article, we learned about length-based operations (with.Java).

We're going to learn about it by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given a list num_list of integers, complete the solution function so that it returns the sum of all elements in the list if the length of the list is 11 or greater, or the product of all elements if the length of the list is 10 or less.

##### Example input and output

| num_list                                | result |
| --------------------------------------- | ------ |
| [3, 4, 5, 2, 5, 4, 6, 7, 3, 7, 2, 2, 1] | 51     |
| [2, 3, 4, 5]                            | 120    |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 1;
        if(num_list.length > 10){
            for(int i = 0; i < num_list.length; i++){
                answer += num_list[i];
            }
            } answer = answer - 1;
        }else {
            for(int i = 0; i < num_list.length; i++){
                answer = answer * num_list[i];
            }
        }
        } return answer;
    }
}
```

##### solution description

int answer = 1;: Initialize the variable answer to store the result. The initial value is 1.

if(num_list.length > 10): If the length of the input array num_list is greater than 10:

Add the sum of all elements in the array to answer.

Subtract 1 at the end to calculate the result.

else: Otherwise (if the length of the array is 10 or less):

Store the result of multiplying all the elements in the array in answer.

return answer;: Returns the calculated result.
