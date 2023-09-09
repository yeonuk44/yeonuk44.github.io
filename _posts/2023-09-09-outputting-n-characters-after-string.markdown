---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Outputting_n_Characters_After_String
title: For outputting n characters after a string (with.Java)
# title: For outputting n characters after a string (with.Java)

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
date: 2023-09-09 09:00:00 +0900
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

### For outputting n characters after a string (with.Java)

{:data-align="center"}

<!-- outline-end -->

We're going to learn as we go along by solving coding test problems, looking back at the problems we solved, and exploring other ways to solve them.

Let's start with the problem.

#### Problem

Given a string my_string and an integer n as parameters, write a solution function that returns a string of n characters after my_string.

##### Example input and output

my_string: "ProgrammerS123"

n: 11

result: "grammerS123"

The last 11 characters in my_string are "grammerS123", so we return this string.

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
class Solution {
    public String solution(String my_string, int n) {
        String answer = "";
        answer = my_string.substring(my_string.length() - n);
        return answer;
    }
}
```

##### Explanation of the solution

Since my_string is supplied as a string, we thought we could just truncate the trailing elements with substring and output them in the answer variable as my_string.substring(my_string.length() - n); for a total length of n, and output the trailing elements by index.

This is possible because substring() returns a value for truncation.

The reason we subtracted n from the full length is because if we just did substring(n), it would truncate the string from the 11th index of my_string when n is 11 because of the nature of substring, and we would get 123.

So if you do the opposite and insert the entire length of my_string minus n into the substring, you'll be left with just that value, and the trailing string will be truncated by the substring and returned.

In this case, we've implemented it so that the n characters after the string are output.
