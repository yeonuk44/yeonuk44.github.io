---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Check_If_It_Is_A_Prefix
title: Check if it's a prefix (with.Java)
# title: Check if it's a prefix (with.Java)

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
date: 2023-09-08 09:00:00 +0900
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

### This article explains how to check if a prefix is a prefix (with.Java).

{:data-align="center"}

<!-- outline-end -->

We're going to solve a coding test problem, reflect on the problem we solved, and learn about other ways to solve it.

Let's start with the problem.

#### Problem

For any string, a prefix means the string up to a certain index. For example, all prefixes for "banana" are "b", "ba", "ban", "bana", "banan", and "banana".

Given a string my_string and is_prefix, write a solution function that returns 1 if is_prefix is a prefix of my_string and 0 otherwise.

##### Example input and output

my_string: "banana"

is_prefix: "ban"

result: 1

This returns 1 because is_prefix is the prefix of my_string.

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public int solution(String my_string, String is_prefix) {
        int answer = 0;
        ArrayList<String> arr = new ArrayList<String>();
        for(int i = my_string.length(); i > 0; i--){
            arr.add(my_string.substring(0,i));
        }

        } answer = arr.contains(is_prefix) ? 1 : 0;
        return answer;
    }
}
```

##### Solution Explained

In the previous post, the suffix was solved by creating a string containing the last character one by one and storing it in an array. This time, the problem is with the prefix.

If we look at substing() again, we see that when we enter only one param, it is recognized as startIndex, and it returns a value of the form (startIndex, string length).

Since we're creating a prefix this time, the startIndex should always be 0, and the last indexes should be decremented by one.

To match that logic, we've set the initial value to my_string.length() to traverse the loop and stop traversal when i reaches zero.

The reason for this is that substring(0,0) will return nothing, so if the loop is traversed with a zero in it, an empty string will be included in arr and allocated useless memory.

We then decrement i by 1 and have it return 0 if any of the elements in arr stored in answer have the same value as is_prefix, and 1 if none.
