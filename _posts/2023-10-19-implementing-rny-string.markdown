---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_rny_String
title: About implementing rny_string (with.Java)
# title: About implementing rny_string (with.Java)
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
date: 2023-10-19 09:00:00 +0900
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

### In this article, we learned about implementing rny_string.

We'll do this by solving coding test problems, reflecting on the problems we solved, and learning about other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

We want to play a trick on a string by taking advantage of the fact that "m" and "rn" look similar.

Given a string rny_string, write a solution function that returns a string with all the "m"s in rny_string replaced with "rn".

##### Example input and output

| rny_string    | result         |
| ------------- | -------------- |
| "masterpiece" | "rnasterpiece" |
| "programmers" | "programmers"  |
| "jerry"       | "jerry"        |
| "burn"        | "burn"         |

#### My solution to the problem

```java
class Solution {
    public String solution(String rny_string) {
        StringBuilder answer = new StringBuilder(rny_string);
        for(int i = 0; i < answer.length(); i++){
            if(answer.charAt(i) == 'm'){
                answer.replace(i,i,"rn");
            }
        }
        } return answer.toString();
    }
}
```

##### Solution

StringBuilder answer = new StringBuilder(rny_string);: Converts the given string rny_string into a StringBuilder object that can be modified. StringBuilder is a class for efficiently modifying strings.

for(int i = 0; i < answer.length(); i++): Starts a loop that traverses the string character by character. The loop is repeated for the length of the string.

if(answer.charAt(i) == 'm'): Checks if the character at the current index i is 'm'.

answer.replace(i, i + 1, "rn");: Replace 'm' with "rn" The replace method replaces the string between starting index i and ending index i + 1 with "rn".

return answer.toString();: Converts the StringBuilder object back to a string and returns the result.

The code implemented in this way generates and returns a new string by replacing all the "m" characters in the input string with "rn". We are working efficiently by using StringBuilder for string modification.
