---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Cut_And_Save_As_Array
title: Cut and save as array (with.Java)
# title:Cut and save as array (with.Java)
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
date: 2024-04-24 09:00:00 +0900
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

## This is an article about the problem of "Cut and save as an array (with.Java)".

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When the strings my_str and n are given as parameters, complete the solution function to return an array that cuts my_str by length n and stores it.

#### Restrictions

- 1 ≤ length of my_str ≤ 100
- 1 ≤ n ≤ length of my_str
- my_str consists of lowercase letters, uppercase letters, and numbers.

#### Input/Output Example

| my_str             | n   | result                       |
| ------------------ | --- | ---------------------------- |
| "abc1Addfggg4556b" | 6   | ["abc1Ad", "dfggg4", "556b"] |
| "abcdef123"        | 3   | ["abc", "def", "123"]        |

<!-- | my_string | result |
| --------- | -------- |
| "Bcad" | "abcd" |
| "heLLo" | "ehllo" |
| "Python" | "hnopty" | -->

### My solution to the problem

```java
class Solution {
     public String[] solution(String my_str, int n) {
         int length = my_str.length();
         int arrayLength = (int) Math.ceil((double) length / n);

         String[] answer = new String[arrayLength];

         for (int i = 0; i < arrayLength; i++) {
             int start = i * n;
             int end = Math.min(start + n, length);
             answer[i] = my_str.substring(start, end);
         }

         return answer;
     }
}
```

### Solution explanation

- Calculate string length: Calculate the length of the given string and store it in the length variable.
- Calculating the length of the array to be divided: To calculate the length of the array to divide the string into, divide the string length by the given length, perform a rounding operation, and add one array if the remainder occurs. Store this value in the arrayLength variable.
- Create an array to store the results: Create a string array of length arrayLength and store it in the answer variable.
- Divide the string into a certain length and store it in an array: Divide the string into a certain length through a for loop and store each substring in the answer array. The starting index is calculated as `i * n`, the ending index is start + n, but if it is the last part, it cannot be greater than the length of the string, so we use Math.min to choose the smaller of the two values.
- Return result array: Returns an answer array containing the divided substrings.

**Code Advantages**

- Flexibility of dividing a string by a certain length: Provides a general way to divide a given string into a desired length and store it in an array.
- Dynamically adjust the size of the array according to the length of the string: Use memory efficiently by dynamically adjusting the size of the array according to the length of the input string.

**Code Disadvantages**

- Array size may vary depending on string length: The size of the array may vary depending on the length of the string and the given length, which may result in unexpected memory usage.
- Immutability of arrays of split substrings: Once a split substring is stored in an array, it cannot be changed, and the substring cannot be modified later.
