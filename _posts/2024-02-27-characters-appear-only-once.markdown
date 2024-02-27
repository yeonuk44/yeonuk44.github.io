---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Characters_Appear_Only_Once
title: Characters that appear only once (with.Java)
# title: Characters that appear only once (with.Java)
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
date: 2024-02-27 09:00:00 +0900
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

## This article looks into the “character that appears only once” issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The string s is given as a parameter.

Complete the solution function to return a string that sorts alphabetically the characters that appear only once in s.

If there are no characters that appear only once, an empty string is returned.

#### Restrictions

- 0 < length of s < 1,000
- s consists of lowercase letters only.

#### Input/Output Example

| s           | result |
| ----------- | ------ |
| "abcabcadc" | "d"    |
| "abdc"      | "abcd" |
| "hello"     | "eho"  |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
import java.util.*;

class Solution {
     public String solution(String s) {
         String answer = "";
         String[] strArr = s.split("");
         int count;
         Arrays.sort(strArr);

         for(String str : strArr){
             count = 0;

             for(int i = 0; i < strArr.length; i++){
                 if(strArr[i].equals(str)){
                     count++;
                 }
             }

             if(count == 1){
                 answer += str;
             }
         }
         return answer;
     }
}
```

### Solution explanation

- First, declare answer, which is an empty string. Then, the given string is divided into individual characters and stored in the strArr array. And then sort the strArr array in ascending order.
- Use the for-each statement to perform the following for each element, str, of the strArr array.
- Initialize the count variable to 0.
- Use the for statement to traverse the strArr array and compare the current element and str for equality. If they are equal, increment count.
- Add the character to the answer only if count is 1, that is, if the current character is not duplicated.
- Returns an answer when all iterations are complete. Therefore, the solution method returns a new string consisting of non-duplicate characters from the given string.
