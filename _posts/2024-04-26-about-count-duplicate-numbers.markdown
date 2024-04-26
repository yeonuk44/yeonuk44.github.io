---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Count_Duplicate_Numbers
title: Count duplicate numbers (with.Java)
# title: Count duplicate numbers (with.Java)
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
date: 2024-04-26 09:00:00 +0900
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

## This is an article about the "Number of duplicate numbers (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When an array containing integers and an integer n are given as parameters, complete the solution function to return how many n are in the array.

#### Restrictions

- 1 ≤ length of array ≤ 100
- 0 ≤ element of array ≤ 1,000
- 0 ≤ n ≤ 1,000

#### Input/Output Example

| array              | n   | result |
| ------------------ | --- | ------ |
| [1, 1, 2, 3, 4, 5] | 1   | 2      |
| [0, 2, 3, 4]       | 1   | 0      |

<!-- | array | result |
| ----------- | ------ |
| [7, 77, 17] | 4 |
| [10, 29] | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int[] array, int n) {
         int answer = 0;
         for(int i = 0; i < array.length; i++){
             if(array[i] == n){
                 answer++;
             }
         }
         return answer;
     }
}
```

### Solution explanation

The solution was solved by sequentially comparing the value of n starting from index 0 and increasing the value of the answer by 1 if the value is found.
