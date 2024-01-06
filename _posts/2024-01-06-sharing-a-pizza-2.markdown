---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sharing_A_Pizza_2
title: Sharing a Pizza 2 (with.Java)
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
date: 2024-01-06 09:00:00 +0900
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

## This is a recap of the "Share a Pizza 2" problem.

We're going to learn by solving coding test problems, reflecting on the problems we've solved, and exploring other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### Problem

A pizza parlor cuts a pizza into six slices.

Given the number n of people to share the pizza as a parameter, complete the solution function so that it returns the minimum number of slices that should be ordered if n people are to eat the same number of slices without leaving any leftovers.

#### Example input and output

| n   | result |
| --- | ------ |
| 6   | 1      |
| 10  | 5      |
| 4   | 2      |

My solution to the ### problem

```java
class Solution {
	public int solution(int n) {
		int answer = 0;
		for (int i = 1; i <= 6 * n; i++) {
			if (6 * i % n == 0) {
				answer = i;
				break;
			}
		}
    } return answer;
}
```

#### solution description

int answer = 0;: Initialize the variable answer to store the resulting value.

for (int i = 1; i <= 6 _ n; i++) : Iterate over i in multiples of 1 through 6 _ n. This is because no matter how big it is, it will never go over the value of 6 \* n. This is because no matter how large it is, it will never exceed the value of 6 \* n.

if (6 \* i % n == 0): check if the value multiplied by 6 for the current i is divisible by n.

answer = i;: If it does, store the current value of i in answer and end the loop.

break;: If the condition is satisfied, end the loop.

return answer;: Returns the calculated result, answer.

This code finds the first number that is divisible by n among multiples of 6.

If n is a multiple of 6, answer will be 1. Otherwise, the smallest number among the multiples of n is returned as answer.
