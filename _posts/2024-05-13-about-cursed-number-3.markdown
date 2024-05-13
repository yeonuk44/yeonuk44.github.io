---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Cursed_Number_3
title: Cursed number 3 (with.Java)
# title: Cursed number 3 (with.Java)
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
date: 2024-05-13 09:00:00 +0900
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

## This is an article looking into the "Curse Number 3 (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

3x Villagers do not use multiples of 3 and the number 3 because they consider 3 to be a cursed number.

When the integer n is given as a parameter, complete the solution function to return n by replacing it with the number used in 3x Village.

#### Restrictions

- 1 ≤ n ≤ 100

#### Input/Output Example

<!-- | keyinput | board | result |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1] |
| ["down", "down", "down", "down", "down"] | [7, 9] | [0, -4] | -->

| n   | result |
| --- | ------ |
| 15  | 25     |
| 40  | 76     |

### My solution to the problem

```java
class Solution {
     public int solution(int n) {
         int answer = 0;
         for(int i = 1; i <= n; i++){
             answer++;
             while(answer % 3 == 0 || String.valueOf(answer).contains("3")){
                 answer++;
             }
         }

         return answer;
     }
}
```

### Solution explanation

Set the answer variable to its initial value of 0.

This variable represents the result.

Execute the loop while increasing the i variable from 1 to n.

Increments the answer variable by 1.

Run the loop as long as the answer variable is a multiple of 3 or the string contains "3" after conversion to a number.

Each time the loop is executed, the answer variable is incremented by 1.

When the loop ends, the answer variable is returned.

**Advantages**

Performs a function that counts the number of numbers within a given range that are multiples of 3 or contain 3 in the number.

The code is concise and easy to understand.

**disadvantage**

Because it is implemented by increasing the answer variable by 1 and checking whether the conditions are met, the efficiency may be low in certain ranges.

Converting the answer variable to a string to check if it contains "3" may result in a performance penalty.

**Improvements**

Instead of using a loop to increment the answer variable by 1, you can improve performance by using a method to directly find numbers that are multiples of 3 or contain 3 in the number.

For example, to find multiples of 3, you can count in a range by increments of 3.

To check whether a number contains 3, you can divide the number by 10 and check the remainder.
