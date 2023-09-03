---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Concatenate_Letters_To_Create_A_String
title: How to concatenate letters to create a string (with.Java)
# title: How to concatenate letters to create a string (with.Java)
# concatenate letters to create a string

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
date: 2023-09-01 09:00:00 +0900
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

### In this article, we learned about How to concatenate characters to create a string (with.Java)

{:data-align="center"}

<!-- outline-end -->

We're going to learn by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.
Let's start with the problem.

#### Problem

Given a string my_string and an array of integers index_list as parameters, write a solution function that returns a string concatenating the letters of the indexes corresponding to the elements of index_list in my_string.

##### Example input and output

my_string: "cvsgiorszzzmrpaqpe"
index_list: [16, 6, 5, 3, 12, 14, 11, 11, 17, 12, 7]
result: "programmers"

In my_string in Example 1, the letters corresponding to indexes 3, 5, 6, 11, 12, 14, 16, and 17 are g, o, r, m, r, a, p, and e, respectively, so the letters of the indexes corresponding to the elements in index_list in my_string are p, r, o, g, r, a, m, m, m, e, r, and s, in that order. Therefore, we return "programmers".

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public String solution(String my_string, int[] index_list) {
        String answer = "";
        ArrayList<Character> arr = new ArrayList<Character>();

        for(int i = 0; i < index_list.length; i++){
            arr.add(my_string.charAt(index_list[i]));
        }
        for(int j = 0; j < arr.size(); j++){
            answer += arr.get(j);
        }
        } return answer;
    }
}
```

##### Solution Explained

The problem is to sequentially extract the elements of index_list from my_string, store them, and print them.
Therefore, we need to index the string. So, we create an array arr, which is an ArrayList, as a Character and get the string as an index one by one.
So I use the .charAt() function to extract my_string one by one by index and save it. Then in answer, I store the arr of type character in a loop.
