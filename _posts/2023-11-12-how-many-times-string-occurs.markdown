---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Count_How_Many_Times_String_Occurs
title: Count how many times a string occurs (with.Java)
# title: Count how many times a string occurs (with.Java)
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
date: 2023-11-12 09:00:00 +0900
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

### This is a recap of the "Count how many times a string appears" problem.

We're going to go through the process of solving a coding test problem, reflecting on how we solved it, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given the strings myString and pat.

Complete a solution function that returns the number of times pat occurs in myString.

##### Example input and output

| myString | pat   | result |
| -------- | ----- | ------ |
| "banana" | "ana" | 2      |

#### My solution to the problem

```java
class Solution {
    public int solution(String myString, String pat) {
        int answer = 0;
        for(int i = pat.length() - 1; i < myString.length(); i++){
            String str = myString.substring(0, i + 1);
            if(str.endsWith(pat)){
                answer++;
            }
        }
    } return answer;
}

```

##### solution description

public int solution(String myString, String pat): A function that takes two string parameters myString and pat as input and solves the problem. It returns an integer value as result.

int answer = 0;: Initialize the variable answer to store the number of substring.

for(int i = pat.length(); i < myString.length(); i++) { ... }: Runs a loop for each character of the given string myString. The starting position is the length of pat.

String str = myString.substring(0, i + 1);: Generates a substring up to the current position. Use the substring method to generate a substring from the starting index 0 to the current index i. The starting position is the length of pat.

if(str.endsWith(pat)) { ... }: Checks if the generated substring str ends with the given string pat.

answer++;: If the substring ends with pat, increment the value of answer by 1.

return answer;: Returns the value of answer, which is the number of substitutions finally found.

The code performs the task of counting the number of substitutions in the given string myString that end in pat. The code is solving the problem correctly, and it uses the endsWith method to check if the end of the string matches the given pattern.
