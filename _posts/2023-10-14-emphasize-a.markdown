---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Emphasize_A
title: Emphasize A (with.Java)
# title: Emphasize A (with.Java)
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
date: 2023-10-14 09:00:00 +0900
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

### This is an article about emphasizing A.

We're going to be solving coding test questions, reflecting on the problems we solved, and learning about other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given a string myString.

Complete the solution function by converting all occurrences of the alphabet "a" in myString to "A" and all non-capitalized alphabets to lowercase alphabets and return.

##### Example input and output

| myString           | result             |
| ------------------ | ------------------ |
| "abstract algebra" | "AbstrAct AlgebrA" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public String solution(String myString) {
        StringBuilder result = new StringBuilder();
        for (int i = 0; i < myString.length(); i++) {
            char currentChar = myString.charAt(i);
            if (currentChar == 'a') {
                result.append('A');
            }else if(currentChar == 'A'){
                result.append(currentChar);
            }else if (Character.isUpperCase(currentChar)) {
                result.append(Character.toLowerCase(currentChar));
            }else {
                result.append(currentChar);
            }
        }
        } return result.toString();
    }
}
```

##### Solution Explained

The above code converts the string by traversing the given string character by character and checking for conditions.

If the character is 'A', it is kept as is, and if it is in the uppercase alphabet, it is converted to lowercase.

Other characters are kept intact.

Considering the performance of string operations, it is implemented to use StringBuilder to construct the string.
