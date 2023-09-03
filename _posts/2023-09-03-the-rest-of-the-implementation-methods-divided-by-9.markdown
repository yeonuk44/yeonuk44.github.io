---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Rest_Of_The_Implementation_Methods_Divided_By_9
title: For the rest of the implementation methods divided by 9 (with. Java)
# title: For the rest of the implementation methods divided by 9 (with. Java)

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
date: 2023-09-03 09:00:00 +0900
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

### In this article, we learned about For the rest of the implementation methods divided by 9 (with. Java)

{:data-align="center"}

<!-- outline-end -->

We're going to learn as we go along, solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.
Let's start with the problem.

#### Problem

It is known that the remainder of a non-negative integer divided by 9 is equal to the sum of each digit of that integer divided by 9.
Use this fact to write a solution function that, given a non-negative integer as a string number, returns the remainder of that integer divided by 9.

##### Example input and output

number: "78720646226947352489"
result: 2

The number is 78720646226947352489 and the sum of the digits is 101.
The remainder of 101 divided by 9 is 2, which is actually 78720646226947352489 = 9 × 8746738469660816943 + 2.
Therefore, it returns 2.

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
class Solution {
    public int solution(String number) {
        int answer = 0;
        int temp = 0;
        for(int i = 0; i < number.length(); i++){
            temp += (number.charAt(i) - '0');
        }

        answer = temp % 9;
        return answer;
    }
}
```

##### Solution

Declare the variable temp to temporarily store an integer value.
Iterate over the length of number, and store all the elements of number together in temp.
(number.charAt(i) - '0'); For this code, we utilized the charAt() function to convert number, which is a list of integers in one string, to a character type and count them one by one.
This function can be used as it is when returning as a String, but when returning as an Integer, it is received as ASCII and must be subtracted by the string '0' to be recognized as the integer type we intended.
If it is returned directly as an integer without subtraction, it will be returned with 48 added during the char to int conversion. **This is because '0' is 48, which is the Ascii code value of 48.**
If the loop completes correctly, we end up with ANSWER returning the value of temp % 9.
