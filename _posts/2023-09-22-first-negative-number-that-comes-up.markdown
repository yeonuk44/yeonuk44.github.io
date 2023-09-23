---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_First_Negative_Number_That_Comes_Up
title: The first negative number that comes up (with.Java)
# title: The first negative number that comes up (with.Java)

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
date: 2023-09-22 09:00:00 +0900
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

### How to First negative number to appear (with.Java)

coding test problem, we'll do a retrospective on the problem we solved and explore other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Complete the solution function so that, given a list of integers num_list, it returns the index of the first negative number that occurs. If there is no negative number, return -1.

##### Example input and output

| num_list                    | result |
| --------------------------- | ------ |
| [12, 4, 15, 46, 38, -2, 15] | 5      |
| [13, 22, 53, 24, 15, 6]     | -1     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
        for(int i = 0; i < num_list.length; i++){
            if(num_list[i] < 0){
                answer = i;
                break;
            } else answer = -1;
        }
        return answer;
    }
}
```

##### Solution Description

int answer = 0;: Initialize the variable answer to store the result to be returned. answer is initialized to 0, which is the default value when no negative value is found.

for(int i = 0; i < num_list.length; i++): Iterate over the array num_list, checking each element.

if(num_list[i] < 0): Checks if the current element is negative.

answer = i;: If a negative value is found, store the current index i in answer and end the loop.

break;: Terminate the loop if a negative value is found.

else answer = -1;: If no negative value is found, set answer to -1. This indicates when no negative values are found in the array.

return answer;: Finally, return answer. This is the index of the first negative value found in the array, or -1 if no negative values are found.
