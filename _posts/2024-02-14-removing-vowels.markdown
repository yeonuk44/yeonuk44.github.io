---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Removing_Vowels
title: Removing vowels (with. Java)
# title: Removing vowels (with. Java)
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
date: 2024-02-14 09:00:00 +0900
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

## This article looks into the “vowel removal” issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

In English, the five letters a, e, i, o, and u are classified into vowels.

Complete the solution function so that when the string my_string is given as a parameter, it returns a string with the vowels removed.

#### Restrictions

- my_string consists of lowercase letters and spaces.
- 1 ≤ length of my_string ≤ 1,000

#### Input/Output Example

| my_string          | result      |
| ------------------ | ----------- |
| "bus"              | "bs"        |
| "nice to meet you" | "nc t mt y" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public String solution(String my_string) {
         StringBuilder answer = new StringBuilder();
         char[] arrString = my_string.toCharArray();

         for(char charString : arrString){
             if(charString != 'a' && charString != 'e' && charString != 'i' && charString != 'o' && charString != 'u'){
                 answer.append(charString);
             }
         }
         return answer.toString();
     }
}
```

### Solution explanation

solution(String my_string): Extracts and returns characters excluding vowels from the given string my_string.

Use StringBuilder to process strings efficiently.

Convert the string to an array of characters, check for each character if it is a collection, and if not, add it to the StringBuilder.

Finally, we convert the StringBuilder to a string and return the result.

**Code Advantages**

- Efficient string processing: String processing is performed efficiently using StringBuilder.
- Concise implementation: Provides a concise implementation through vowel checking for each character.

**Code Disadvantages**

- Hard-coded vowel list: When checking vowels, 'a', 'e', 'i', 'o', and 'u' are hard-coded, so if the vowel changes later, the code must be modified.
