---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Paper_Cutting
title: Paper Cutting (with.Java)
# title: Paper Cutting (with.Java)
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
date: 2024-05-27 09:00:00 +0900
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

## This is an article about the "Paper Cutting (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

I'm trying to cut a large piece of paper into 1 x 1 pieces.

For example, cutting a 2 x 2 piece of paper into a 1 x 1 piece requires at least three strokes of the scissors.

When integers M and N are given as parameters, complete the solution function to return the minimum number of times a piece of paper of size M x N must be scissored.

#### Restrictions

- 0 < M, N < 100
- Paper cannot be overlapped and cut.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| M   | N   | result |
| --- | --- | ------ |
| 2   | 2   | 3      |
| 2   | 5   | 9      |
| 1   | 1   | 0      |

### My solution to the problem

```java
class Solution {
 public int solution(int M, int N) {
 int answer = (M * N) - 1;
 return answer;
 }
}
```

### Solution review

This is a function that calculates the number of cells remaining in a grid-shaped area excluding one cell using the given M and N.

First, declare the variable answer and initialize it to `(M * N) - 1`.

This is the total number of cells in the grid minus one.

Finally, it returns an answer.
