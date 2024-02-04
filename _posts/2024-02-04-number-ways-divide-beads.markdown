---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Ways_Divide_Beads
title: Number of ways to divide beads (with.Java)
# title: Number of ways to divide beads (with.Java)
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
date: 2024-02-04 09:00:00 +0900
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

## This is an article that examines the “number of ways to divide marbles” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

I'm planning to share the beads with my friends.

The beads all look different.

When balls, the number of marbles the mage has, and share, the number of marbles to share among the balls, are given as parameters, complete the solution function that returns the number of all possible cases of selecting the share number of marbles among the balls.

#### Restrictions

1 ≤ balls ≤ 30

1 ≤ share ≤ 30

The order in which beads are selected is not taken into account.

share ≤ balls

#### Input/Output Example

| balls | share | result |
| ----- | ----- | ------ |
| 3     | 2     | 3      |
| 5     | 3     | 10     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int balls, int share) {
         double answer = 1;

         for(int i = 0; i < share; i++){
             answer = answer * (balls - i) / (i+1);
         }

         return(int)answer;
     }
}
```

### Solution explanation

We are efficiently calculating the number of cases by using factorial calculations to find the binomial coefficients.

The result is converted from double to int and returned. If the number becomes very large, you can initialize the answer to 1 and continue accumulating it, exceeding the range of the integer.

Casting to double and later converting back to int may be incorrect.

Calculations on large numbers have the potential for integer overflow.

So for calculations on larger numbers you can consider long or BigInteger.

#### Points that can be improved

Casting Note: For accuracy in integer calculations, keep the answer as double when calculating it and consider casting if necessary.

Mathematical optimization: Efficiency can be improved by considering mathematical optimization when calculating the number of cases.

Prevent integer overflow: Use long or BigInteger to prevent overflow when calculating the number of cases for large numbers.
