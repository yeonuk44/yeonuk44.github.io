---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_H_Index
title: H-Index (with.Java)
# title: Letter (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, sort]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-05 09:00:00 +0900
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

## This is an article about the H-Index (with.Java) problem.

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

The H-Index is an indicator of a scientist's productivity and influence.

You want to find the value h that represents the H-Index of a scientist.

According to Wikipedia 1, H-Index is obtained as follows.

Of the n papers published by a scientist, if more than h are cited and the rest are cited less than h, the maximum value of h is this scientist's H-Index.

Write a solution function to return this scientist's H-Index, given the sequence citations of the number of citations of a paper published by a scientist as a parameter.

#### Restrictions

- The number of papers published by scientists is more than one and less than 1,000.
- The number of citations per paper is 0 or more and 10,000 or less.

#### Input/Output Examples

| citations       | return |
| --------------- | ------ |
| [3, 0, 6, 1, 5] | 3      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### my solution to the problem

```java
import java.util.Arrays;

class Solution {
    public int solution(int[] citations) {
        int answer = 0;
        Arrays.sort(citations);
        for(int i = 0; i < citations.length; i++){
            int temp = Math.min(citations[i], citations.length - i);
            if(temp >= answer){
                answer = temp;
            }else{
                break;
            }
        }
        return answer;
    }
}
```

### Solution Description

- The solution method takes integer array citations as input.
- First, sort the citations arrays in ascending order, which is a common approach to sort the arrays to calculate the H-Index.
- Then use the for loop to traverse the array.
- Choose a smaller value between each citation count citations[i] and the remaining number of citations.length -i, which makes the current H-Index candidate.
- If the current H-Index candidate is greater or equal to the previous H-Index candidate, update the answer.
- The subsequent values are smaller, meaning that the H-Index is no longer increasing, so end the iteration with break.
- Finally, answer is returned.

### Conclusion

The code solves the problem of computing H-Index using an array of number of thesis citations, which uses an iterative statement to find and verify H-Index candidates after arranging the arrays.
