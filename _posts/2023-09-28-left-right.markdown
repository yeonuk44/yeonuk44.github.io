---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Left_Right
title: Left Right (with.Java)
# title: Left Right (with.Java)

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
date: 2023-09-28 09:00:00 +0900
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

### This is a post about left-right (with.Java).

We'll be solving coding test questions, reflecting on the problems we've solved, and learning about other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

#### Problem

A list of strings, str_list, contains a number of the four strings "u", "d", "l", and "r".

Complete the solution function to return an ordered list of strings to the left of "l" and "r" in str_list if "l" comes first, and an ordered list of strings to the right of "r" if "r" comes first.

If there is no "l" or "r", return an empty list.

##### Example input and output

| str_list             | result     |
| -------------------- | ---------- |
| ["u", "u", "l", "r"] | ["u", "u"] |
| ["l"]                | []         |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public String[] solution(String[] str_list) {
        int lIndex = -1;
        int rIndex = -1;

        for (int i = 0; i < str_list.length; i++) {
            if (str_list[i].equals("l")) {
                lIndex = i;
                break;
            } else if (str_list[i].equals("r")) {
                rIndex = i;
                break;
            }
        }
        if (lIndex == -1 && rIndex == -1) {
            return new String[0];
        }

        if (lIndex != -1) {
            String[] answer = new String[lIndex];
            for (int j = 0; j < lIndex; j++) {
                answer[j] = str_list[j];
            }
            } return answer;
        }
        else {
            String[] answer = new String[str_list.length - rIndex - 1];
            for (int k = rIndex + 1; k < str_list.length; k++) {
                answer[k - rIndex - 1] = str_list[k];
            }
            } return answer;
        }
    }
}
```

##### solution description

int lIndex = -1;, int rIndex = -1;: Initialize the index of the "l" character and the index of the "r" character. The initial values are set to -1.

First iteration (for (int i = 0; i < str_list.length; i++) {): Loops through the array str_list, looking for the character "l" or "r". If an "l" is found, store its index in lIndex and exit the loop; if an "r" is found, store its index in rIndex and exit the loop.

if (lIndex == -1 && rIndex == -1) { return new String[0]; }: If neither "l" nor "r" is found, return an empty string array.

if (lIndex != -1) { ... } else { ... }: Performs different logic depending on if either "l" or "r" was found.

If "l" is found:

String[] answer = new String[lIndex];: Create an array answer to store the strings before the "l" character.

Use a loop to copy the strings before the "l" character into the answer array.

Return the answer array.

If an "r" is found:

String[] answer = new String[str_list.length - rIndex - 1];: Create an array answer to store the strings after the "r" character.

Use a loop to copy the strings after the "r" character into the answer array.

Return the answer array.
