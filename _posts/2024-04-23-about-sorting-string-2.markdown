---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sorting_String_2
title: Sorting strings 2 (with.Java)
# title: Sorting strings 2 (with.Java)
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
date: 2024-04-23 09:00:00 +0900
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

## This is an article about the problem of "Sort strings 2 (with.Java)".

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When a string my_string consisting of upper and lower case English letters is given as a parameter, complete the solution function to change my_string to all lowercase letters and return a string sorted in alphabetical order.

#### Restrictions

- 0 < my_string < 100

#### Input/Output Example

| my_string | result   |
| --------- | -------- |
| "Bcad"    | "abcd"   |
| "heLLo"   | "ehllo"  |
| "Python"  | "hnopty" |

### My solution to the problem

```java
import java.util.Arrays;

class Solution {
     public String solution(String my_string) {
         String answer = my_string.toLowerCase();

         char[] chars = answer.toCharArray();
         Arrays.sort(chars);
         answer = new String(chars);
         return answer;
     }
}
```

### Solution explanation

- Lowercase conversion: Converts the given string to lowercase using the toLowerCase method.
- Convert to and sort a character array: Use the toCharArray method to convert a string to a character array, and use the Arrays.sort method to sort the character array alphabetically.
- Convert to string: Convert the sorted character array back to a string and save it in the answer.
- Return result: Returns the final sorted string.

**Code Advantages**

- Simple string sorting: You can easily convert and sort strings to lowercase by utilizing Java's built-in methods.
- Code conciseness: Strings are handled in a simple yet effective way.

**Code Disadvantages**

- No handling of Unicode characters: The current code performs sorting on ASCII characters. To properly handle Unicode characters, you need to consider another approach.
- Ignoring string immutability: Since strings are immutable, the process of converting a sorted character array back to a string may seem unnecessary. This part can be optimized.
- No exception handling when the string is null: The current code does not consider handling when the given string is null. I recommend adding exception handling for null.
- No handling if string contains spaces: The current code sorts without considering spaces within the string. If you want to include spaces in the sorting, you need to modify that part.
