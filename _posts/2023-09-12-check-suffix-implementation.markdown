---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Check_Suffix_Implementation
title: About the Check Suffix Implementation (with.Java)
# title: About the Check Suffix Implementation (with.Java)

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
date: 2023-09-12 09:00:00 +0900
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

### In this article, we learned how to implement Flip a String Multiple Times (with.Java).

We've been solving coding test problems, reflecting on the problems we've solved, and learning about other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

For some strings, a suffix means a string starting at a certain index.

For example, all suffixes for "banana" are "banana", "anana", "nana", "ana", "na", and "a".

Given a string my_string and is_suffix, write a solution function that returns 1 if is_suffix is a suffix of my_string and 0 otherwise.

##### Example input and output

my_string: "banana"

is_suffix: "ana"

result: 1

This returns 1 because is_suffix is the suffix of my_string.

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public int solution(String my_string, String is_suffix) {
        int answer = 0;
        ArrayList<String> arr = new ArrayList<String>();

        for(int i = 0; i < my_string.length(); i++){
            arr.add(my_string.substring(i));
        }

        } answer = arr.contains(is_suffix) ? 1 : 0;
        return answer;
    }
}
```

##### Explanation of the solution

The way to store all the suffixes in an array is to strip them off one character at a time and store them in an array.

To do this, we used substring() to insert a loop into the ArrayList, traversing the length of the string to be suffixed with my_string.length().

We then need to check that the string in is_suffix is the suffix contained in the arr element.

We do that by checking the ArrayList's contains() to see if the element exists, and then print it out with a value in answer depending on whether it's true or false.
