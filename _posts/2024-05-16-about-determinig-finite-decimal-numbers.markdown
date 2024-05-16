---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Determinig_Finite_Decimal_Numbers
title: Determining finite decimal numbers (with.Java)
# title: Determining finite decimal numbers (with.Java)
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
date: 2024-05-16 09:00:00 +0900
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

## This is an article about the problem of "Identifying finite decimal numbers (with.Java)".

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

A decimal number that has only a finite number of digits after the decimal point and does not continue is called a finite decimal number.

When converting a fraction to a decimal, we want to determine whether the fraction can be expressed as a finite decimal number.

The conditions for a fraction to become a finite decimal number are as follows.

When expressed as an irreducible fraction, the only prime factors in the denominator must be 2 and 5.

When two integers a and b are given as parameters, complete the solution function so that it returns 1 if a/b is a finite decimal number and 2 if it is an infinite decimal number.

#### Restrictions

- a, b are integers
- 0 < a ≤ 1,000
- 0 < b ≤ 1,000

#### Input/Output Example

<!-- | lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| a   | b   | result |
| --- | --- | ------ |
| 7   | 20  | 1      |
| 11  | 22  | 1      |
| 12  | 21  | 2      |

### My solution to the problem

```java
class Solution {
     public int solution(int a, int b) {
         int answer = 0;
         int temp = b / GCD(a, b);

         while(temp != 1){
             if(temp % 2 == 0){
                 temp /= 2;
             }else if(temp % 5 == 0){
                 temp /= 5;
             }else {
                 answer = 2;
                 return answer;
             }
         }

         answer = 1;

         return answer;
     }

     private int GCD(int a, int b){
             if(b == 0){
                 return a;
             }else{
                 return GCD(b, a % b);
             }
         }
}
```

### Solution explanation

Stores the value of dividing b by the greatest common divisor (GCD) of a and b in the variable temp.

To do this, we call the GCD method.

The loop is performed until temp becomes 1.

Check if temp is divisible by 2 or 5.

If it is divisible, divide the corresponding values by 2 and 5, respectively, and then update temp again.

If temp is not divisible by 2 or 5, we set answer to 2 and return this value.

If all conditions pass, set answer to 1 and return this value.

This code efficiently solves the problem by determining the relationship between two given numbers.

In particular, the key to solving the problem is determining whether it is divisible by using the greatest common divisor.
