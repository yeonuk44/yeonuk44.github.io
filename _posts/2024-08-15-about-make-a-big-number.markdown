---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Make_A_Big_Number
title: Make a big number (with.Java)
# title: Make a big number (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding tes, greedy]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-15 09:00:00 +0900
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

## This is an article about the problem of making large numbers (with.Java).

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

You want to find the largest number you can get when you remove k from a number.

For example, if you remove two numbers from the number 1924, you can create [19, 12, 14, 92, 94, 24].

The largest number of these is 94.

The number of numbers and the number k to be removed in string format are given as parameters of the solution function.

Complete the solution function so that when you remove k numbers from the number, you return the largest number you can create in the form of a string.

#### Restrictions

- Number is a number greater than or equal to 2 digits and less than 1,000,000 digits.
- k is a natural number greater than or equal to one number and less than one digit.

#### Input/Output Examples

| number       | k   | return   |
| ------------ | --- | -------- |
| "1924"       | 2   | "94"     |
| "1231234"    | 3   | "3234"   |
| "4177252841" | 4   | "775841" |

### my solution to the problem

```java
class Solution {
    public String solution(String number, int k) {
        String answer = "";
        StringBuilder sb = new StringBuilder();
        int idx = 0;
        int num;
        for(int i = 0; i < number.length() - k; i++){
            num = 0;
            for(int j = idx; j <= k + i; j++){
                if(num < number.charAt(j) - '0'){
                    num = number.charAt(j) - '0';
                    idx = j + 1;
                }
            }
            sb.append(num);
        }
        return sb.toString();
    }
}
```

### Solution Description

- Use StringBuilder sb to save the results.
- The idx variable represents the index of the number selected so far.
- The num variable stores the largest number of the selected numbers.
- The outer iteration repeats until the resulting string is number.length() -k.
- The inner iteration selects the largest number among the remaining numbers, excluding the number selected so far.
- Adds the largest number selected to the result.

### Conclusion

This code solves the problem using the Greedy method.

The Greedy method is an algorithm that makes the best choice right now at each stage and consequently finds the optimal solution.
