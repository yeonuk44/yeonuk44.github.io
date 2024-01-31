---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Discount_Clothing_Store
title: Get a discount at a clothing store (with.Java)
# title: Get a discount at a clothing store (with.Java)

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
date: 2024-01-31 09:00:00 +0900
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

## This article looks into the problem of “getting a discount at a clothing store.”

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Mooseuk’s Clothing Store offers a 5% discount for purchases over 100,000 won, a 10% discount for purchases over 300,000 won, and a 20% discount for purchases over 500,000 won.
Given the price of the clothes purchased, complete the solution function to return the amount to be paid.

#### Restrictions

10 ≤ price ≤ 1,000,000
The price is given in units of 10 won (1's place is 0).
Returns an integer with decimal places truncated.

#### Input/Output Example

| price   | result  |
| ------- | ------- |
| 150,000 | 142,500 |
| 580,000 | 464,000 |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int price) {
         int discount = 0;
         if (price >= 500000) {
             discount = price / 5;
         } else if (price >= 300000) {
             discount = price / 10;
         } else if (price >= 100000) {
             discount = price / 20;
         }
         System.out.println(price - discount);
         return price - discount;
     }
}
```

### Solution explanation

int discount = 0;: Initializes the variable discount to store the discount amount.

if (price >= 500000): If the input price is more than 500,000:

discount = price / 5;: Calculates a 20% discount on the price.

else if (price >= 300000): If the input price is greater than 300,000 and less than 500,000:

discount = price / 10;: Calculates a 10% discount on the price.

else if (price >= 100000): If the input price is greater than 100,000 and less than 300,000:

discount = price / 20;: Calculates a 5% discount on the price.

System.out.println(price - discount);: Prints the discounted price.

return price - discount;: Returns the discounted price.

### Explanation of changed restrictions

If we round the decimal point instead of returning an integer with the decimal point rounded off, how can we solve this if we calculate to the nearest 1 won?

#### My solution to the changed restrictions problem

```java
class Solution {
     public int solution(int price) {
         int discount = 0;
         if (price >= 500000) {
             discount = (int) Math.ceil(price * 0.2);
         } else if (price >= 300000) {
             discount = (int) Math.ceil(price * 0.1);
         } else if (price >= 100000) {
             discount = (int) Math.ceil(price * 0.05);
         }
         return price - discount;
     }
}
```

#### Solving the problem of changed restrictions

int discount = 0;: Initializes the variable discount to store the discount amount.

if (price >= 500000): If the input price is more than 500,000:

discount = (int) Math.ceil(price \* 0.2);: Calculates a 20% discount on the price, and rounds up using the Math.ceil function.

else if (price >= 300000): If the input price is greater than 300,000 and less than 500,000:

discount = (int) Math.ceil(price \* 0.1);: Calculate the 10% discount of the price and round up using the Math.ceil function.

else if (price >= 100000): If the input price is greater than 100,000 and less than 300,000:

discount = (int) Math.ceil(price \* 0.05);: Calculate the 5% discount of the price and round up using the Math.ceil function.

return price - discount;: Calculates and returns the discounted price.
