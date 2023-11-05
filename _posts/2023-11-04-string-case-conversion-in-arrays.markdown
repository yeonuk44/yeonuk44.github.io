---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_String_Case_Conversion_In_Arrays
title: String Case Conversion in Arrays (with.Java)
# title: String Case Conversion in Arrays (with.Java)
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
date: 2023-11-04 09:00:00 +0900
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

### In this article, we learned how to convert a string case in an array.

We'll do so by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of strings, strArr.

Complete the solution function that returns the string at the odd-numbered index in the array with all characters uppercase and the string at the even-numbered index with all characters lowercase, given that all elements are alphabetic.

##### Example input and output

| strArr                    | result                    |
| ------------------------- | ------------------------- |
| ["AAA","BBB","CCC","DDD"] | ["aaa","BBB","ccc","DDD"] |
| ["aBc","AbC"]             | ["abc","ABC"]             |

#### My solution to the problem

```java
class Solution {
    public String[] solution(String[] strArr) {
        String[] answer = new String[strArr.length];
        for(int i = 0; i < strArr.length; i++){
            if(i % 2 == 0){
                answer[i] = strArr[i].toLowerCase();
            } else{
                answer[i] = strArr[i].toUpperCase();
            }
        }
        } return answer;
    }
}
```

##### solution description

String[] answer = new String[strArr.length];: Create a string array answer to store the result. Create it with the same length as the input array.

for(int i = 0; i < strArr.length; i++) : Iterate over the input array strArr, examining each string.

if(i % 2 == 0) : If the current index i is an even number:

Convert the current string to lowercase and store it in the answer array.

else : If the current index i is odd:

Convert the current string to uppercase and store it in the ANSWER array.

return answer;: Returns the answer array with the conversion done for all strings.

This code creates and returns a new array with the strings at even indices in the input array converted to lowercase and the strings at odd indices converted to uppercase.
