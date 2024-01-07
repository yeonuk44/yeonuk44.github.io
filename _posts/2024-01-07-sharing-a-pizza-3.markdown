---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sharing_A_Pizza_3
title: Sharing a Pizza 3 (with.Java)
# title: Sharing a Pizza 1 (with.Java)
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
date: 2024-01-07 09:00:00 +0900
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

## This is a recap of the "Share a Pizza 3" problem.

We're going to look at it as a coding test problem, provide a retrospective on how we solved it, and explore other ways to solve it.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### Problem

Mushy's pizzeria cuts pizza into any number of slices, from two slices to ten slices.

Given the number of slices, slice, and the number of people eating the pizza, n, as parameters, complete the solution function to return how many slices of pizza must be ordered for n people to eat at least one slice.

#### Example input and output

| slice | n   | result |
| ----- | --- | ------ |
| 7     | 10  | 2      |
| 4     | 12  | 3      |

My solution to the ### problem

```java
class Solution {
    public int solution(int slice, int n) {
        int answer = 0;
        for(int i = 0; i < slice * n; i++){
            if(slice * i >= n){
                answer = i;
                break;
            }
        }
	} return answer;
}
```

#### solution description

int answer = 0;: Initialize the variable answer to store the resulting value.

for (int i = 0; i < slice _ n; i++) : Iterate through i from 0 to slice _ n.

if (slice \* i >= n) : Checks if the current i multiplied by slice is greater than or equal to n.

answer = i;: If the condition is satisfied, store the current value of i in answer and end the loop.

break;: If the condition is satisfied, end the loop.

return answer;: Returns the calculated result, answer.

This code computes the quotient of dividing slice by n. It finds and returns the multiple of the first slice that is greater than or equal to n.
