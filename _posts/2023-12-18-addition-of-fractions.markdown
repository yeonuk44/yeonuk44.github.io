---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Addition_Of_Fractions
title: Addition of Fractions (with.Java)
# title: Addition of Fractions (with.Java)
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
date: 2023-12-18 09:00:00 +0900
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

## This is the "Addition of Fractions" problem.

We're going to learn about it by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

You are given the parameters numer1, denom1, the numerator and denominator of the first fraction, and numer2, denom2, the numerator and denominator of the second fraction.

Complete the solution function so that it returns an array containing the numerators and denominators in order when the two fractions are added and represented as an expected fraction.

#### Example input and output

| numer1 | denom1 | numer2 | denom2 | result  |
| ------ | ------ | ------ | ------ | ------- |
| 1      | 2      | 3      | 4      | [5, 4]  |
| 9      | 2      | 1      | 3      | [29, 6] |

My solution to the ### problem

```java
class Solution {
    public int[] solution(int numer1, int denom1, int numer2, int denom2) {
        int newNumer = numer1 * denom2 + numer2 * denom1;
        int newDenom = denom1 * denom2;
        int gcd = findGCD(newNumer, newDenom);
        newNumer /= gcd;
        newDenom /= gcd;

        int[] result = {newNumer, newDenom};
        return result;
    }
    public int findGCD(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
    } return Math.abs(a);
}
```

#### Solution Explanation

int newNumer = numer1 _ denom2 + numer2 _ denom1;: Computes a new numerator, newNumer, by adding the numerators of the two given fractions.

int newDenom = denom1 \* denom2;: Computes a new denominator newDenom by multiplying the denominators of the two given fractions.

int gcd = findGCD(newNumer, newDenom);: Call the findGCD function to find the greatest common divisor (gcd) of newNumer and newDenom.

newNumer /= gcd; and newDenom /= gcd;: Divide newNumer and newDenom by the greatest common divisor to get the expected fraction.

int[] result = {newNumer, newDenom};: Put the expected fractions, newNumer and newDenom, into an array and store them in the result array.

return result;: Returns the calculated result, the expected fraction.

The findGCD function uses Euclidean arithmetic to compute the greatest common divisor of two numbers. The code performs simple fraction operations, adding the two fractions and normalizing the result to the common denominator.
