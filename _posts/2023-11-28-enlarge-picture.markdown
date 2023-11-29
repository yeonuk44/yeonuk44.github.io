---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Enlarge_Picture
title: Enlarge Picture (with.Java)
# title: Enlarge Picture (with.Java)
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
date: 2023-11-28 09:00:00 +0900
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

## This is the "Enlarge Picture" problem.

We're going to learn by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### Problem

You have a rectangular-shaped picture file, which is made up of 1 × 1 square-sized pixels.

Given a string array picture representing this picture file and an integer k as parameters, write a solution function that returns a string array that represents the picture file stretched k times horizontally and vertically.

#### Example input and output

| picture               | k   | result                                                                                                                             |
| --------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------- |
| ["x.x", ".x.", "x.x"] | 3   | ["xxx...xxx", "xxx...xxx", "xxx...xxx", "...xxx...", "...xxx...", "...xxx...", "xxx...xxx", "xxx...xxx", "xxx...xxx", "xxx...xxx"] |

My solution to the ### problem

```java
class Solution {
    public String[] solution(String[] picture, int k) {
        int rows = picture.length;
        int cols = picture[0].length();

        String[] answer = new String[rows * k];

        StringBuilder tempStr = new StringBuilder();
        int count = 0;

        for (String str : picture) {
            for (int i = 0; i < str.length(); i++) {
                char ch = str.charAt(i);
                for (int j = 0; j < k; j++) {
                    tempStr.append(ch);
                }
            }

            for (int j = 0; j < k; j++) {
                answer[count++] = tempStr.toString();
            }

        } tempStr.setLength(0);
    }

} return answer;
```

#### solution description

int rows = picture.length; and int cols = picture[0].length();: Count the number of rows and columns in the given picture array.

String[] answer = new String[rows * k];: Create a new string array answer to store the result. The size of the array will be rows \* k.

StringBuilder tempStr = new StringBuilder();: Create a StringBuilder object tempStr to store the temporary string.

int count = 0;: Initialize the variable count to keep track of the index of the result array answer.

for (String str : picture) : Iterates over each string str in the given array of pictures.

for (int i = 0; i < str.length(); i++) : Iterating over each character of the string str:

Get the character ch.
Repeat that character ch k times and add it to tempStr.
for (int j = 0; j < k; j++) : Repeat the string tempStr k times and add it to the answer array.

tempStr.setLength(0);: Empty the temporary string tempStr.

return answer;: Returns the newly created string array answer.
