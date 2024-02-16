---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Addition_Of_Hidden_Numbers_1
title: Addition of hidden numbers 1 (with.Java)
# post specific
# title: Addition of hidden numbers 1 (with.Java)
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
date: 2024-02-16 09:00:00 +0900
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

## This is an article about the "Addition of hidden numbers 1" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The string my_string is given as a parameter.

Complete the solution function to return the sum of all natural numbers in my_string.

#### Restrictions

- 1 ≤ length of my_string ≤ 1,000
- my_string consists only of lowercase letters, uppercase letters, and one-digit natural numbers.

#### Input/Output Example

| my_string       | result |
| --------------- | ------ |
| "aAb1B2cC34oOp" | 10     |
| "1a2b3c4d123"   | 16     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(String my_string) {
         int answer = 0;
         for (char ch : my_string.toCharArray()) {
             if (Character.isDigit(ch)) {
                 answer += Character.getNumericValue(ch);
             }
         }
         return answer;
     }
}
```

### Solution explanation

- solution(String my_string): Extracts a number from the given string my_string and returns the result of adding the extracted numbers.
- int answer: Variable to store the final result.
- While iterating through the string, use Character.isDigit(ch) to check whether each character is a number. If it is a number, use Character.getNumericValue(ch) to accumulate and add the numbers.
- Returns the final added value.

**Code Advantages**

- Easy to add numbers: The process of extracting numbers from each letter and adding them is simple and intuitive.

**Code Disadvantages**

- Number range limitation: The code extracts only numbers from 0 to 9 from the string and adds them. If you need a different number range, you will need to modify your code.
