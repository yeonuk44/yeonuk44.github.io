---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Addition_Of_Hidden_Numbers_2
title: Addition of hidden numbers 2 (with.Java)
# title: Addition of hidden numbers 2 (with.Java)
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
date: 2024-05-07 09:00:00 +0900
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

## This is an article about the problem “Addition of hidden numbers 2 (with.Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The string my_string is given as a parameter.

my_string consists only of lowercase letters, uppercase letters, and natural numbers.

Complete the solution function to return the sum of the natural numbers in my_string.

#### Restrictions

- 1 ≤ length of my_string ≤ 1,000
- 1 ≤ natural number in my_string ≤ 1000
- Consecutive numbers are considered one number.
- There is no case where there is a leading 0, such as 000123.
- If there are no natural numbers in the string, please return 0.

#### Input/Output Example

<!-- | keyinput | board | result |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1] |
| ["down", "down", "down", "down", "down"] | [7, 9] | [0, -4] | -->

| my_string       | result |
| --------------- | ------ |
| "aAb1B2cC34oOp" | 37     |
| "1a2b3c4d123Z"  | 133    |

### My solution to the problem

```java
class Solution {
 public int solution(String my_string) {
 int answer = 0;
 String[] strArr = my_string.replaceAll("[a-zA-Z]", " ").split(" ");

 for(String str : strArr){
 if(!str.equals("")){
 answer += Integer.valueOf(str);
 }
 }
 return answer;
 }
}
```

### Solution explanation

- Alphabet substitution and string separation: Replaces the alphabet with spaces in a given string, separates the results based on spaces, and creates a string array.
- Number extraction and summation: Iterate through the string array, convert each element to a number, and sum the converted numbers. Empty strings are ignored.
- Return result: Returns the summed result.

**Code pros and cons**

- Pro: Used regular expressions to replace alphabets with spaces and easily split strings. The code is written to be concise and easy to understand.
- Disadvantage: This code assumes that the input fits the given format. Exception handling is required when malformed input is given. In the process of separating and summing strings, additional string arrays are created, which uses more memory.
