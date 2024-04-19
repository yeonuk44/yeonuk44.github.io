---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Adding_Digits
title: Adding digits (with.Java)
# title: Adding digits (with.Java)
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
date: 2024-04-19 09:00:00 +0900
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

## This is an article about the "digit addition (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When an integer n is given as a parameter, complete the solution function to return the sum of each digit of n.

#### Restrictions

- 0 ≤ n ≤ 1,000,000

#### Input/Output Example

| n      | result |
| ------ | ------ |
| 1234   | 10     |
| 930211 | 16     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int n) {
         int answer = 0;
         String str = Integer.toString(n);
         for(int i = 0; i < str.length(); i++){
             int k = (int)str.charAt(i) - '0';
             answer += k;
         }
         return answer;
     }
}
```

### Solution explanation

Method signature: public int solution(int n)
This is a method that takes the integer n as a parameter and returns an integer value.

Initialize variable: int answer = 0;
Initialize answer, the variable to store the result value, to 0.

Converting an integer to a string: String str = Integer.toString(n);
Convert the input integer n to a string and store it in str.

Loop through the string and add the digits of each digit:
for(int i = 0; i < str.length(); i++)
Repeat for the length of the string.

int k = (int)str.charAt(i) - '0';
Get the ith character from the string, find the ASCII code value, subtract the ASCII code value of '0', convert the result to an integer, and store it in k.

answer += k;
Add the value k to the answer.

Return result value: return answer;
Returns the value stored in the answer variable.

In this way, the code returns the value of adding each digit of the given integer.
