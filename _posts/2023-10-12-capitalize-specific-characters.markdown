---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Capitalize_Specific_Characters
title: Capitalize specific characters (with.Java)
# title:  Capitalize specific characters (with.Java)
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
date: 2023-10-12 09:00:00 +0900
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

### In this article, we learned how to capitalize certain characters.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given a string my_string of lowercase letters and a string alp of one lowercase letter as parameters, write a solution function that returns a string that capitalizes all the letters in my_string that correspond to alp.

##### Example input and output

| myString      | alp | result        |
| ------------- | --- | ------------- |
| "programmers" | "p" | "Programmers" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public String solution(String my_string, String alp) {
        StringBuilder answer = new StringBuilder();
        for(int i = 0; i < my_string.length(); i++){
            char currentChar = my_string.charAt(i);
            if(currentChar == alp.charAt(0)){
                answer.append(Character.toUpperCase(currentChar));
            } else{
                answer.append(currentChar);
            }
        }
        } return answer.toString();
    }
}
```

##### solution description

public String solution(String my_string, String alp): A function that takes two string parameters my_string and alp as input and processes the string.

StringBuilder answer = new StringBuilder();: Creates a StringBuilder object to hold the resulting string. We will use this object to construct the string.

for(int i = 0; i < my_string.length(); i++) { ... }: Execute a loop for each character in the given string my_string.

char currentChar = my_string.charAt(i);: Store the character of the string currently being processed by the iterator in the currentChar variable.

if(currentChar == alp.charAt(0)) { ... } else { ... }: Compare if the current character is equal to the given character alp.

answer.append(Character.toUpperCase(currentChar));: If the current character is equal to the given character alp, convert it to upper case and add it to the result string answer.

answer.append(currentChar);: If the current character is different from the given character alp, keep it as is and add it to the result string answer.

return answer.toString();: Finally, return the string stored in answer as a string.
