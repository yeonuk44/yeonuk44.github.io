---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Create_With_l
title: Create with l (with.Java)
# title: Create with l (with.Java)
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
date: 2023-12-06 09:00:00 +0900
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

## This is the "Make it L" problem.

We're going to learn about it by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### Problem

You are given a string, myString, consisting of lowercase letters of the alphabet.

Complete the solution function to return a string that replaces all characters that precede "l" in the alphabetical order with "l".

#### Example input and output

| myString     | result       |
| ------------ | ------------ |
| "abcdevwxyz" | "lllllvwxyz" |
| "jjnnllkkmm" | "llnnllllmm" |

My solution to the ### problem

```java
class Solution {
    public static String solution(String myString) {
        char[] charArray = myString.toCharArray();
        for (int i = 0; i < charArray.length; i++) {
            if (charArray[i] < 'l') {
                charArray[i] = 'l';
            }
        }
    } return new String(charArray);
}
```

#### solution

char[] charArray = myString.toCharArray();: Converts the input string myString to the character array charArray. This allows us to access the string on a character-by-character basis.

for (int i = 0; i < charArray.length; i++) : Iterate through the character array charArray, performing an action on each character.

if (charArray[i] < 'l') : If the current character is a character that is lexicographically ahead of 'l':

Replace that character with 'l'.

return new String(charArray);: Convert the changed character array charArray back to a string and return it.
