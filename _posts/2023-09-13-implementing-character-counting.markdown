---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_Character_Counting
title: About implementing character counting (with.Java)
# title: About implementing character counting (with.Java)

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
date: 2023-09-13 09:00:00 +0900
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

In this article, we looked at implementing ### character counting (with.Java).

We'll be solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given a string my_string that contains only alphabetical characters.

count of 'A' in my_string, count of 'B' in my_string,..., count of 'Z' in my_string, count of 'a' in my_string, count of 'b' in my_string,...

Write a solution function that returns an array of integers of length 52 containing the number of occurrences of 'z' in my_string in order.

##### Example input and output

my_string: "Programmers"

result: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 2, 0, 1, 0, 0, 0, 3, 1, 0, 0, 0, 0, 0, 0, 0, 0]

In my_string, there is one 'P', one 'a', one 'e', one 'g', two 'm', one 'o', three 'r', and one 's', so.

returns [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 0, 2, 0, 1, 0, 0, 0, 3, 1, 0, 0, 0, 0, 0, 0, 0, 0].

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
class Solution {
    public int[] solution(String my_string) {
        int[] answer = new int[52];
        for (int i = 0; i < my_string.length(); i++) {
            char c = my_string.charAt(i);

            if (c >= 'A' && c <= 'Z') {
                answer[c - 'A']++;
            } else if (c >= 'a' && c <= 'z') {
                answer[26 + c - 'a']++;
            }
        }

        return answer;
    }
}
```

##### Solution

This code counts the frequency of occurrence of alphabetical characters within the given string my_string.

The result is returned as an array of int[], where each element of the array represents the number of occurrences of a particular alphabetical character.

The answer array is an integer array of length 52, storing counts for the uppercase and lowercase letters of the alphabet, respectively.

Indexes 0 through 25 store the number of occurrences of the uppercase letters 'A' through 'Z'.

Indexes 26 through 51 store the number of occurrences of lowercase letters 'A' through 'Z'.

**Here's how the code works:**

Iterate over the length of my_string, checking for each letter c.

If c is an uppercase letter, subtract 'A' to find the position of that uppercase letter, and increment the count at that position. (answer[c - 'A']++)

If c is a lowercase letter, subtract 'a' and add 26 to find the corresponding lowercase letter and increment the count at that position. (answer[26 + c - 'a']++)

When it has finished processing all the characters, it returns an array of answer. This array represents the number of occurrences of each letter of the alphabet in the string.
