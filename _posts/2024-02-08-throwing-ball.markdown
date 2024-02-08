---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Throwing_Ball
title: Throwing a ball (with.Java)
# title: Throwing a ball (with.Java)
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
date: 2024-02-08 09:00:00 +0900
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

## This is an article about the “ball throwing” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

I'm standing in a circle with my shy friends and playing a game of throwing a ball.

The ball is thrown starting from number 1, and you can skip one person to the right and throw only to the next person.

Given an integer array numbers containing friends' numbers and an integer K, complete the solution function to return the number of the kth person who throws the ball.

#### Restrictions

- 2 < length of numbers < 100
- 0 < k < 1,000
- The first and last numbers in numbers are actually right next to each other.
- Numbers start from 1 and go up in order.

#### Input/Output Example

| numbers            | k   | result |
| ------------------ | --- | ------ |
| [1, 2, 3, 4]       | 2   | 3      |
| [1, 2, 3, 4, 5, 6] | 5   | 3      |
| [1, 2, 3]          | 3   | 2      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int[] numbers, int k) {
         int answer = 0;
         answer = numbers[2 * (k -1) % numbers.length];
         return answer;
     }
}
```

### Solution explanation

Here numbers.length represents the length of the array numbers.

In the given problem, we throw the ball, skipping one person to the right. To implement this, we multiply (k - 1) by 2 and use the remainder divided by numbers.length.

By doing this, we can find the number of the kth thrower, skipping one person to the right.

For example, let's consider the case where the array numbers is [1, 2, 3, 4, 5] and k is 3.

- Initially, 1 throws the ball. (0th shy)
- Next, 3 throws the ball. (2nd shy)
- And 5 throws the ball. (4th shy)
  The code that expresses this is numbers[2 * (k - 1) % numbers.length].

By using the remainder operator, we can iterate through the array and find the number of the kth thrower.

**addition**
You can use the remainder operator to loop through an array.

If the length of the array is n, for index i, i % n is repeated while cycling through the array.

When using this to retrieve the value at a specific position from an array, you can conveniently implement a circular operation by using the remainder divided by the length of the array.

For example, if the length of the array is 5:

- 0 % 5 is 0
- 1% 5 is 1
- 2% 5 is 2
- 3% 5 is 3
- 4% 5 is 4
- 5% 5 is 0 again
- 6% 5 is 1

If you calculate the index of the array through the remainder operation in this way, you can achieve the effect of rotating the array.

This provides easy access to periodically repeated array elements.
