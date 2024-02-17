---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Length_Of_Array_Elements
title: Length of array elements (with. Java)
# title: Length of array elements (with. Java)
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
date: 2024-02-17 09:00:00 +0900
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

## This is an article that looks into the “length of array elements” issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

A string array strlist is given as a parameter.

Complete the solution function to retrun an array containing the length of each element of strlist.

#### Restrictions

- 1 ≤ length of strlist element ≤ 100
- strlist consists of lowercase letters, uppercase letters, and special characters.

#### Input/Output Example

| strlist                        | result       |
| ------------------------------ | ------------ |
| ["We", "are", "the", "world!"] | [2, 3, 3, 6] |
| ["I", "Love", "Programmers."]  | [1, 4, 12]   |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int[] solution(String[] strlist) {
         int[] answer = new int[strlist.length];
         int count = 0;
         for(String temp : strlist){
             answer[count++] = temp.length();
         }
         return answer;
     }
}
```

### Solution explanation

- Array initialization: Initialize the array answer to store the result as long as the given string array strlist through int[] answer = new int[strlist.length];
- Calculating string length: While iterating through the array strlist using a for-each statement, calculate the length of each string with temp.length() and store it in the answer array at the corresponding index.
- Index increase: After storing the length of each string, the count variable is increased so that the value can be stored at the next index.
- Result return: Calculate the length of all strings, store them in an array, and finally return the result array answer.

**Code Advantages**

- Simple logic: It consists of simple yet efficient logic that calculates the length of the string.
- Scalability: Array initialization is performed dynamically so that it can respond flexibly according to the length of the array, making it possible to respond to a variety of inputs.

**Code Disadvantages**

- Lack of error handling: The current code does not consider exception handling, such as when the input array is null. It is a good idea to add appropriate exception handling.
- Fixed return value data type: The current code returns the result array as int[], but there is a lack of logic to respond when various data types are required depending on the input. There is a need to improve it by considering the diversity of inputs and returns.
