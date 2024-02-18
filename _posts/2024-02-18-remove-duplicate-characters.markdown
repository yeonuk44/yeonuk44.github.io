---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Remove_Duplicate_Characters
title: Remove duplicate characters (with.Java)
# title: Remove duplicate characters (with.Java)
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
date: 2024-02-18 09:00:00 +0900
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

## This article looks into the “removing duplicate characters” issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The string my_string is given as a parameter.

Please complete the solution function to remove duplicate characters from my_string and return a string with only one character remaining.

#### Restrictions

- 1 ≤ my_string ≤ 110
- my_string consists of uppercase letters, lowercase letters, and spaces.
- Distinguish between uppercase and lowercase letters.
- Spaces (" ") are also separated by one character.
- Among the duplicated characters, the first character is left.

#### Input/Output Example

| my_string          | result            |
| ------------------ | ----------------- |
| "people"           | "peol"            |
| “We are the world” | "We are arthwold" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
import java.util.*;
class Solution {
     public String solution(String my_string) {
         StringBuilder answer = new StringBuilder();
         Set<String> set = new HashSet<>();
         char[] arrMyString = my_string.toCharArray();

         for(char ch : arrMyString){
             if(set.add(String.valueOf(ch))){
                 answer.append(ch);
             }
         }

         return answer.toString();
     }
}
```

### Solution explanation

- HashSet utilization: Create a HashSet that does not allow duplication through Set<String> set = new HashSet<>();
- String traversal: After converting the string to a character array, iterate through each character using the for-each statement.
- Removal of duplicates: Add characters to HashSet through set.add(String.valueOf(ch)). If a character already exists, the add method returns false, and if it is a new character, it returns true.
- Add unique character: Only if it is a new character, add the character to the result string through answer.append(ch).
- Result return: After traversing all characters and removing duplicate characters, the resulting string is finally returned through the toString() method.

**Code Advantages**

- Simple logic: A simple yet effective logic is used to remove duplicate characters and leave only unique characters.
- HashSet utilization: HashSet is a data structure that can effectively remove duplicate values, making it easy to check for duplicates.
- String manipulation: Strings are efficiently manipulated using StringBuilder.

**Code Disadvantages**

- Case Sensitivity: The current code is case sensitive and handles duplicate characters. If you want to handle duplicates case-insensitively, additional logic is needed.
- Result string order: The current code does not maintain the order of the strings but removes duplicates. If you want to remove duplicates while maintaining the order of the input string, you should use LinkedHashSet, etc.
- String conversion overhead: The part where characters are converted to strings through String.valueOf(ch) is repeated, which may cause overhead. This may cause performance degradation, especially when processing large strings.
