---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Chicken_Coupon
title: Chicken Coupon (with.Java)
# title: Chicken Coupon (with.Java)
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
date: 2024-05-21 09:00:00 +0900
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

## This is an article about the "Chicken Coupon (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When you order chicken, Programmer's Chicken issues one coupon per chicken.

If you collect ten coupons, you can receive one free chicken, and a coupon will also be issued for the service chicken.

When the number of chickens ordered chicken is given as a parameter, complete the solution function to return the maximum number of served chickens that can be received.

#### Restrictions

- chicken is an integer.
- 0 ≤ chicken ≤ 1,000,000

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| chicken | result |
| ------- | ------ |
| 100     | 11     |
| 1,081   | 120    |

### My solution to the problem

```java
class Solution {
 public int solution(int chicken) {
 int answer = 0;

 while (chicken >= 10) {
 answer += chicken / 10;
 chicken = chicken / 10 + chicken % 10;
 }
 return answer;
 }
}
```

### Solution review

First, we initialize the answer variable to 0.

Use a while loop to iterate only if the number of chickens is 10 or more.

Add 10 divided by the current number of chickens to the answer. This is the number of coupons you can get from the current number of chickens.

Update the number of the next chicken by adding the remainder of dividing the number of chickens by 10 to the quotient of dividing the number of chickens by 10.

By doing this, the number of chickens purchased at one time and the number of chickens received as a coupon are added to calculate the number of chickens in the next step.

When the while loop ends, the number of chickens is less than 10, so the function returns the last calculated answer value.
