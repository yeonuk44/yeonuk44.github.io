---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Ranking
title: Ranking (with. Java)
# title: Ranking (with. Java)
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
date: 2024-05-18 09:00:00 +0900
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

## This is an article that looks into the "ranking (with. Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

We want to rank students based on the average of their English and math scores.

Given a two-dimensional integer array score containing English and math scores, complete the solution function to return an array containing ranks based on the average of the English and math scores.

#### Restrictions

- 0 ≤ score[0], score[1] ≤ 100
- 1 ≤ score length ≤ 10
- The element length of score is 2.
- score does not have duplicate elements.

#### Input/Output Example

<!-- | lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| score                                                                      | result                |
| -------------------------------------------------------------------------- | --------------------- |
| [[80, 70], [90, 50], [40, 70], [50, 80]]                                   | [1, 2, 4, 3]          |
| [[80, 70], [70, 80], [30, 50], [90, 100], [100, 90], [100, 100], [10, 30]] | [4, 4, 6, 2, 2, 1, 7] |

### My solution to the problem

```java
import java.util.*;
class Solution {
 public int[] solution(int[][] score) {
 int[] answer = new int[score.length];
 List<Integer> list = new ArrayList<>();

 for(int[] tempArray : score){
 list.add(tempArray[0] + tempArray[1]);
 }

 list.sort(Comparator.reverseOrder());

 for(int i = 0; i < score.length; i++){
 answer[i] = list.indexOf(score[i][0] + score[i][1]) + 1;
 }
 return answer;
 }
}
```

### Solution explanation

The solution method takes a two-dimensional integer array score as input.

This array represents each student's English and math scores.

First, create a list that will contain the sum of each student's English and math scores.

By iterating through the array score, each student's English score and math score are added together and added to the list.

Sort in descending order based on the combined score.

Once again, iterate over the array score and determine the rank by checking which student's combined score is the largest.

After determining the rank, store that rank in the answer array.

Finally, it returns an answer array.

The reason for ranking students this way is based on the sum of their scores, because using averages can cause decimal problems.
