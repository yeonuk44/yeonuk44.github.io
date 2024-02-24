---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Convert_Text_Number_To_Integer
title: Convert text numbers to integer (with.Java)
# title: Convert text numbers to integer (with.Java)
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
date: 2024-02-24 09:00:00 +0900
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

## This is an article about the problem of "Converting text numbers to integers."

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

A nerd who doesn't like English tries to change numbers written in English into numbers.

When the string numbers are given as a parameter, complete the solution function to return numbers by converting them to an integer.

#### Restrictions

- Numbers consist of lowercase letters only.
- Numbers are a combination of "zero", "one", "two", "three", "four", "five", "six", "seven", "eight", and "nine" without spaces.
- 1 ≤ length of numbers ≤ 50
- "zero" cannot be at the beginning of numbers.

#### Input/Output Example

| numbers                                | result    |
| -------------------------------------- | --------- |
| "onetwothreefourfivesixseveneightnine" | 123456789 |
| "onefourzerosixseven"                  | 14067     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public long solution(String numbers) {
         String string_num = numbers
             .replace("zero", "0")
             .replace("one", "1")
             .replace("two", "2")
             .replace("three", "3")
             .replace("four", "4")
             .replace("five", "5")
             .replace("six", "6")
             .replace("seven", "7")
             .replace("eight", "8")
             .replace("nine", "9");

         long answer = Long.parseLong(string_num);
         return answer;
     }
}
```

### Solution explanation

- Use the replace method on the string numbers to replace numbers in English with the corresponding actual numbers. The replace method replaces the string received as the first argument with the string received as the second argument. In this way, “zero” becomes “0”, “one” becomes “1”, and so on.
- Since the converted string string_num is an actual numeric string, it is converted to a long type number through the Long.parseLong method. This converted long type number is returned as the final result.
- This method converts numbers expressed in English into actual numbers. For example, when the input “onetwothree” comes in, it is converted to “123” and then converted to the number 123 and returned.
- The judgment is based on the ASCII code value for each character. In the ASCII code, 65 to 90 represents uppercase letters A to Z. Therefore, characters that fall within this range are converted to lowercase letters, and characters that do not (i.e. lowercase letters) are converted to uppercase letters.
- The reason for using the char type is that it is suitable for determining the case of letters using ASCII codes. Since the char type can be converted to a number, you can use ASCII code in this way. On the other hand, the String type is a value for the entire string, so it is impossible to use ASCII code directly.
- Methods such as toUpperCase and toLowerCase are methods of the String class, so they can only be used on String objects. Since the char type does not have a method like this, it is used after converting the ch type to the String type for case conversion. This conversion is done via Character.toString(ch).
