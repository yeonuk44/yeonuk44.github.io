---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sorting_Strings_1
title: Sorting strings 1 (with.Java)
# title: Sorting strings 1 (with.Java)
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
date: 2024-02-12 09:00:00 +0900
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

## This is an article that looks into the problem of “sorting strings 1”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When the string my_string is given as a parameter, write a solution function that selects only the numbers in my_string and returns a list sorted in ascending order.

#### Restrictions

- 1 ≤ length of my_string ≤ 100
- my_string contains one or more numbers.
- my_string consists of lowercase English letters or numbers from 0 to 9.

#### Input/Output Example

| my_string   | result          |
| ----------- | --------------- |
| "hi12392"   | [1, 2, 2, 3, 9] |
| "p2o4i8gj2" | [2, 2, 4, 8]    |
| "abcde0"    | [0]             |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
import java.util.*;

class Solution {
     public int[] solution(String my_string) {
         List<Integer> numbers = new ArrayList<>();

         for (char ch : my_string.toCharArray()) {
             if (Character.isDigit(ch)) {
                 numbers.add(Character.getNumericValue(ch));
             }
         }

         Collections.sort(numbers);
         int[] answer = numbers.stream().mapToInt(i -> i).toArray();

         return answer;
     }
}
```

### Solution explanation

solution(String my_string): Extracts numbers from the given string my_string and returns them as a sorted array.

List<Integer> numbers: List to store numbers.

While iterating through the string, use Character.isDigit(ch) to check whether each character is a number. If it is a number, use Character.getNumericValue(ch) to convert the numeric char to int type and add the number to the list.

Collections.sort(numbers): Sorts the numbers in the list in ascending order.

numbers.stream().mapToInt(i -> i).toArray(): Converts a sorted list to an array.

**Code Advantages**

Easy to extract and sort numbers: Provides simple code by utilizing Java's built-in functions and collections to extract and sort numbers.

**Code Disadvantages**

Number range restriction: The code extracts and sorts only the numbers 0 through 9 from the string.

If you need a different number range, you will need to modify the code.
