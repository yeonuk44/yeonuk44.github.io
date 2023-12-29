---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Removing_Specific_Characters
title: Removing Specific Characters (with.Java)
# title: Removing Specific Characters (with.Java)
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
date: 2023-12-29 09:00:00 +0900
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

## This is the "Remove specific characters" problem.

We're going to take a look at solving a coding test problem, provide a retrospective on how we solved it, and explore other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

### Problem

Given a string my_string and a character letter as parameters, complete the solution function so that it returns a string with letter removed from my_string.

#### Limitations

1 ≤ length of my_string ≤ 100

letter is an alphabetic character of length 1

my_string and letter are in alphabetical case.

Distinguish between uppercase and lowercase letters.

#### Example input and output

| my_string | letter | result  |
| --------- | ------ | ------- |
| "abcdef"  | "f"    | "abcde" |
| "CBdbe"   | "B"    | "Cdbe"  |

My solution to the ### problem

```java
class Solution {
    public String solution(String my_string, String letter) {
        StringBuilder result = new StringBuilder();
        for(char ch : my_string.toCharArray()){
            if(ch != letter.charAt(0)){
                result.append(ch);
            }
        }
    } return result.toString();
}
```

#### Solution

This code is a function that creates a new string of characters from the string my_string, excluding the specific character letter. Below is a brief explanation of the main parts of the code.

Short description of the main code

```java
class Solution {
    public String solution(String my_string, String letter) {
        // Create a StringBuilder object to accumulate the resulting string
        StringBuilder result = new StringBuilder();

        // Convert the string my_string to an array of characters and iterate over each character
        for (char ch : my_string.toCharArray()) {
            // only add to the result if the current character is not equal to the character letter to exclude
            if (ch != letter.charAt(0)) {
                result.append(ch);
            }
        }

        // convert the final result to a string and return it
        return result.toString();
    }
}
```

Key steps in that code:

Create a StringBuilder object result to accumulate the final result string.

Convert the string my_string to an array of characters and iterate over each character.

Only add the character to result if the current character is not equal to the character letter to exclude.

Finally, convert result to a string and return it.

For example, calling solution("hello", "l") returns "heo".
