---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Factorial
title: Factorial (with.Java)
# title: Factorial (with.Java)
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
date: 2024-02-13 09:00:00 +0900
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

## This is an article about the “factorial” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

ifactorial (i!) means the product of integers from 1 to i. For example 5! = 5 _ 4 _ 3 _ 2 _ 1 = 120. Given an integer n, complete the solution function to return the largest integer i that satisfies the following conditions.

-i! ≤ n

#### Restrictions

- 0 < n ≤ 3,628,800

#### Input/Output Example

| n       | result |
| ------- | ------ |
| 3628800 | 10     |
| 7       | 3      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int n) {
         int answer = 0;
         int temp = 1;
         for(int i = 2; i <= 10; i++){
             for(int j = i; j >= 2; j--){
                 temp *= j;
             }
             if(temp == n){
                 answer = i;
                 return answer;
             } else if(temp > n){
                 answer = i - 1;
                 return answer;
             } else {
                 temp = 1;
             }
         }
         return answer;
     }
}
```

### Solution explanation

solution(int n): Returns the minimum number of numbers that can represent the given integer n as a factorial.

Use the for statement to calculate the factorial for numbers from 2 to 10.

Calculate the factorial from the current number to 2 through the inner for statement and store it in temp.

If the calculated factorial matches n, that number is returned as the result.

If the factorial is greater than n, the previous number is the minimum number and is returned as the result.

**Code Advantages**

- Simple implementation: The implementation required to solve the problem is simple.
- Intuitive logic: It has intuitive logic by sequentially checking given conditions.

**Code Disadvantages**

- Applicable only to a specific range: Currently, the factorial is calculated only for numbers from 2 to 10, so if it is outside this range, accurate results cannot be obtained.
