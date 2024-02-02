---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Iced_Americano
title: Iced Americano (with.Java)
# title: Iced Americano (with.Java)

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
date: 2024-02-02 09:00:00 +0900
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

## This article looks into the “Iced Americano” issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Even on cold days, I only drink iced Americano.

Iced Americano costs 5,500 won per glass.

Complete the solution function to return an array containing the maximum number of cups of Americano the mugger can drink and the remaining money in order when the money the muggle has is given as a parameter.

#### Restrictions

0 < money ≤ 1,000,000

#### Input/Output Example

| money  | result    |
| ------ | --------- |
| 5,500  | [1, 0]    |
| 15,000 | [2, 4000] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int[] solution(int money) {
         int[] answer = new int[2];
         answer[0] = money / 5500;
         answer[1] = money % 5500;
         return answer;
     }
}
```

### Solution explanation

int[] answer = new int[2];: Creates an array answer to store two integers.

answer[0] = money / 5500;: Stores the quotient of the input amount money divided by 5500 in the first element of the array. This indicates how many times it is divisible by 5500.

answer[1] = money % 5500;: Divide the input amount money by 5500 and store the remainder in the second element of the array. This represents the amount remaining when divided by 5500.

return answer;: returns an array answer where the calculated quotient and remainder are stored.

This code divides the entered amount by 5500 and returns the quotient and remainder in an array.
