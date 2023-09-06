---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_Suffix_Arrays
title: About Implementing Suffix Arrays (with.Java)
# title: About Implementing Suffix Arrays (with.Java)

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
date: 2023-09-06 09:00:00 +0900
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

### Implementing a suffixed array (with.Java).

{:data-align="center"}

<!-- outline-end -->

We're going to learn by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.
Let's start with the problem.

#### Problem

For some strings, a suffix means a string starting at a certain index.
For example, all suffixes for "banana" are "banana", "anana", "nana", "ana", "na", and "a".
Given a string my_string as a parameter, write a solution function that returns an array of strings sorted alphabetically by all suffixes in my_string.

##### Example input and output

my_string: "banana"
result: ["a", "ana", "anana", "banana", "na", "nana"]

In other words, my_string is "banana" and all suffixes are like the description in the question.
Sorting it alphabetically would return ["a", "ana", "anana", "banana", "na", "nana"] because it is "a", "ana", "anana", "banana", "na", "nana".

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public String[] solution(String my_string) {
        ArrayList<String> arr = new ArrayList<String>();
        for(int i = 0; i < my_string.length(); i++){
            arr.add(my_string.substring(i));
        }
        Collections.sort(arr);
        String[] answer = new String[arr.size()];
        for(int j = 0; j < arr.size(); j++){
            answer[j] = arr.get(j);
        }
        } return answer;
    }
}
```

##### Explanation of the solution

The way to store all the suffixes in an array is to strip them off one character at a time and store them in an array.
To do this, we used substring() to insert a loop into an ArrayList, iterating over the length of the string to be suffixed with my_string.length().
This actually separated all the suffixes, but for the required result, I wanted them to be sorted in pre-edited order, so I used Collections' sort() to sort the elements in the array.
