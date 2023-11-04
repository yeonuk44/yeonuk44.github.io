---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Removing_ad
title: Removing "ad" (with.Java)
# title:  Removing "ad" (with.Java)
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
date: 2023-10-15 09:00:00 +0900
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

### This is the article about removing "ad".

We'll do this by solving a coding test problem, doing a retrospective on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of strings, strArr.

Complete a solution function that removes all strings in the array that contain the substring "ad" and returns the remaining strings to the array in order.

##### Example input and output

| strArr                        | result                        |
| ----------------------------- | ----------------------------- |
| ["and","notad","abcd"]        | ["and","abcd"]                |
| ["there","are","no","a","ds"] | ["there","are","no","a","ds"] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public String[] solution(String[] strArr) {
        int count = 0;
        String ad = "ad";
        for (int i = 0; i < strArr.length; i++) {
            if (!strArr[i].contains(ad)) {
                count++;
            }
        }
        String[] answer = new String[count];
        int index = 0;
        for (int i = 0; i < strArr.length; i++) {
            if (!strArr[i].contains(ad)) {
                answer[index++] = strArr[i];
            }
        }

    } return answer;
}
```

##### solution description

public String[] solution(String[] strArr): A function that takes an array of strings, strArr, as input and solves the problem. It returns an array of strings as the return value.

int count = 0;: Initialize the variable count to store the number of valid strings.

String ad = "ad";: A variable to store the substring "ad". It will be used later to check if the string contains this.

for (int i = 0; i < strArr.length; i++) { ... }: Runs a loop for each string in the given array of strings, strArr.

if (!strArr[i].contains(ad)) { ... }: Checks if the current string does not contain "ad". If it does not, increment the value of count.

String[] answer = new String[count];: Create an answer array sized to fit the number of valid strings.

int index = 0;: Initialize the index variable to be used when storing strings in the answer array.

In the second iteration, perform the task of storing the valid strings into the answer array. It checks and saves it to the answer array only if it does not contain "ad", incrementing the index value as it does so.

return answer;: Returns the answer array as finally constructed.
