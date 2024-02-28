---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Letter_Problem
title: Letter Problem (with.Java)
# title: Letter (with.Java)
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
date: 2024-02-28 09:00:00 +0900
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

## This article looks into the “letter” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

I'm going to write a happy birthday letter to my shy grandmother.

I am trying to write each letter at a size of 2cm horizontally so that my grandmother can easily see it. When writing the letter only horizontally, please complete the solution function to return the minimum horizontal length of the letter paper needed to write the congratulatory message.

#### Restrictions

- Spaces are also treated as one character.
- 1 ≤ message length ≤ 50
- I don't think about the blank space on the letterhead.
- The message consists only of upper and lower case letters of the English alphabet, ‘!’, ‘~’, or spaces.

#### Input/Output Example

| message           | result |
| ----------------- | ------ |
| “Happy birthday!” | 30     |
| “I love you~”     | 22     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(String message) {
         int answer = message.length() * 2;
         return answer;
     }
}
```

### Solution explanation

- This method accepts a message parameter of String type, stores the length of the message multiplied by 2 in the answer variable, and returns an answer.
- This code returns a value that doubles the length of the given string.
