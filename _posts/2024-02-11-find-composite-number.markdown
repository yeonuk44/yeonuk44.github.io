---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_Composite_Number
title: Find composite number (with.Java)
# title: Find composite number (with.Java)
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
date: 2024-02-11 09:00:00 +0900
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

## This article examines the problem of “Finding composite numbers.”

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

A number with three or more divisors is called a composite number.

When a natural number n is given as a parameter, complete the solution function so that it returns the number of composite numbers less than n.

#### Restrictions

- 1 ≤ n ≤ 100

#### Input/Output Example

| n   | result |
| --- | ------ |
| 10  | 5      |
| 15  | 8      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int n) {
         int answer = 0;
         int count = 0;
         for(int i = 1; i <= n; i++){
             for(int j = 1; j <= i; j++){
                 if(i % j == 0){
                     count++;
                 }
             }
             if(count > 2){
                 answer++;
             }
             count = 0;
         }
         return answer;
     }
}
```

### Solution explanation

solution(int n): Determines whether each number within the given range is prime, and if so, increments the answer.

count: A variable that counts the number of divisors of each number. For decimal numbers, the number of divisors must be 2.

Use the for statement to repeat numbers from 1 to n, and use the nested for statement to find the divisors of each number.

In the inner for statement, if(i % j == 0) is a condition that checks whether j is a divisor of i.

If the number of factors exceeds 2, the number is not prime.

Problem Solving: Solve problems using the simple method of finding the number of prime numbers within a given range.

Intuitive: The code is intuitive and easy to understand.

Although the code is simple, it does not use an efficient prime number discrimination algorithm, so performance may not be good for large input values.

To improve this, it is recommended to use an efficient decimal discrimination algorithm.
