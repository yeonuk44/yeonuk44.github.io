---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Truncate_And_Sort_Strings
title: Truncate and Sort Strings (with.Java)
# title:  Truncate and Sort Strings (with.Java)
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
date: 2023-10-17 09:00:00 +0900
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

### In this article, we learned how to cut and sort a string.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given a string myString.

Complete a solution function that truncates that string based on "x", creates an array, and returns the array sorted alphabetically.

However, do not put the empty string in the array to be returned.

##### Example input and output

myString: "axbxcxdx"

result: ["a","b","c","d"]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public String[] solution(String myString) {

        ArrayList<String> arr = new ArrayList<String>();
        String str = "";
        for(int i = 0; i < myString.length(); i++){
            if(myString.charAt(i) == 'x'){
                arr.add(str);
                str = "";
            }else{
                str += myString.charAt(i);
            }
        }

        if (!str.isEmpty()) {
            arr.add(str);
        }

        arr.removeIf(String::isEmpty);
        Collections.sort(arr);

        String[] answer = new String[arr.size()];
        for(int j = 0; j < answer.length; j++){
            answer[j] = arr.get(j);
        }
        } return answer;
    }
}
```

##### Solution

ArrayList<String> arr = new ArrayList<String>();: Create arr, an ArrayList to store the substring.

String str = "";: Creates an empty string, str, to store the current substring.

for(int i = 0; i < myString.length(); i++) { ... }: Starts a loop that traverses the given string myString character by character.

if(myString.charAt(i) == 'x') { ... }: Checks to see if the current character is "x". If it is "x", add the substring str up to this point to the list arr and initialize str.

Otherwise, append the current character to str.

Traverse the string through the loop, extracting the substring based on "x" and storing it in the arr list.

if (!str.isEmpty()) { arr.add(str); }: For the final substring processing, if str is not empty, add it to the arr list.

arr.removeIf(String::isEmpty);: Remove the empty string from the arr list using the removeIf method.

Collections.sort(arr);: Sort the arr list alphabetically.

String[] answer = new String[arr.size()];: Create the result array answer based on the arr list with the length determined.

for(int j = 0; j < answer.length; j++) { ... }: Copy the substring stored in the arr list to the answer array.

The function ends and returns the answer array. This array contains the substring separated by "x", sorted alphabetically except for the empty string.
