---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Up_To_The_n_Element
title: Up to the nth element (with.Java)
# title: Up to the nth element (with.Java)

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
date: 2023-10-01 09:00:00 +0900
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

### In this article, we've learned about the nth element (with.Java).

We'll do this by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given a list of integers num_list and an integer n, complete the solution function so that it returns a list containing all elements of num_list from the first element to the nth element.

##### Example input and output

| num_list        | n   | result    |
| --------------- | --- | --------- |
| [2, 1, 6]       | 1   | [2]       |
| [5, 2, 1, 7, 5] | 7   | [5, 2, 1] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = new int[n];
        for(int i = 0; i < n; i++){
            answer[i] = num_list[i];
        }
        } return answer;
    }
}
```

##### solution description

int[] answer = new int[n];: Create an integer array answer to store the result. The size of this array is set to n.

for(int i = 0; i < n; i++) : Extract n elements from the beginning of num_list using a loop.

answer[i] = num_list[i];: copy the num_list element at the current index i to the same index in the answer array.

return answer;: Finally return the array answer with n elements from the beginning.
