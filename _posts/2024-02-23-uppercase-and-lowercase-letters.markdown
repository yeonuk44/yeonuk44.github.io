---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Uppercase_And_Lowercase_Letters
title: Uppercase and lowercase letters (with.Java)
# title: Uppercase and lowercase letters (with.Java)
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
date: 2024-02-23 09:00:00 +0900
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

## This article looks into the “uppercase and lowercase letters” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When the string my_string is given as a parameter, complete the solution function to return a string with uppercase letters converted to lowercase and lowercase letters converted to uppercase.

#### Restrictions

- 1 ≤ length of my_string ≤ 1,000
- my_string consists only of uppercase and lowercase English letters.

#### Input/Output Example

| my_string    | result       |
| ------------ | ------------ |
| "cccCCC"     | "CCCccc"     |
| "abCdEfghIJ" | "ABcDeFGHij" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public String solution(String my_string) {
         StringBuilder answer = new StringBuilder();
         char[] chArr = my_string.toCharArray();
         for(char ch : chArr){
             String str = Character.toString(ch);
             if(ch >= 65 && 90 >= ch){
                 answer.append(str.toLowerCase());
             }else{
                 answer.append(str.toUpperCase());
             }
         }
         return answer.toString();
     }
}
```

### Solution explanation

This code is a method that converts all uppercase letters in a given string to lowercase and lowercase to uppercase.

To do this, we create a StringBuilder object and loop through it, converting the string to a char array.

For each character, the decision is made based on the ASCII code value, where 65 to 90 represent uppercase letters A to Z. Therefore, characters that fall within this range are converted to lowercase letters, and characters that do not (i.e. lowercase letters) are converted to uppercase letters.

The reason for using the char type like this is because it is suitable for determining the case of characters using ASCII codes.

Since the char type can be converted to a number, you can use ASCII code in this way.

On the other hand, the String type is a value for the entire string, so it is impossible to use ASCII code directly.

And methods such as toUpperCase and toLowerCase are methods of the String class, so they can only be used on String objects.

Since the char type does not have a method like this, it is used after converting the ch type to the String type for case conversion.

This conversion is done via Character.toString(ch).
