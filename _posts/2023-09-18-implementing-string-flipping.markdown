---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_String_Flipping
title: About implementing string flipping (with.Java)
# title: About implementing string flipping (with.Java)

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
date: 2023-09-18 09:00:00 +0900
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

### Implementing string flipping (with.Java)

We're going to go through a series of coding test problems, providing a retrospective of the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given a string my_string and integers s and e as parameters, write a solution function that returns a string flipped from index s to index e in my_string.

##### Example input and output

| my_string         | s   | e   | result            |
| ----------------- | --- | --- | ----------------- |
| "Progra21Sremm3"  | 6   | 12  | "ProgrammerS123"  |
| "Stanley1yelnatS" | 4   | 10  | "Stanley1yelnatS" |

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
class Solution {
    char[] arr;
    public String solution(String my_string, int s, int e) {

        arr = my_string.toCharArray();

        reverse(s,e);
        return new String(arr);
    }

    private void reverse(int startIdx, int endIdx){
        while(startIdx < endIdx){
            char temp = arr[startIdx];
            arr[startIdx++] = arr[endIdx];
            arr[endIdx--] = temp;
        }
    }
}
```

##### Solution

char[] arr;: Declares a member variable arr for converting a string to an array of characters and storing it.

public String solution(String my_string, int s, int e) : The solution function takes three parameters: my_string is the original string, s is the start index of the part to be flipped, and e is the end index of the part to be flipped.

arr = my_string.toCharArray();: Convert the given string my_string to an array of characters using the toCharArray method, and store it in arr.

reverse(s, e);: Call the reverse method to reverse the substring.

private void reverse(int startIdx, int endIdx) : The reverse method serves to reverse a portion of the character array. flip the characters between startIdx and endIdx.

while(startIdx < endIdx) : Runs a loop until startIdx is less than endIdx.

char temp = arr[startIdx];: temporarily store the character at the current startIdx position in the temp variable.

arr[startIdx++] = arr[endIdx];: Replace the character at position startIdx with the character at position endIdx, and increment startIdx to move to the next character.

arr[endIdx--] = temp;: Replace the character at position endIdx with the value stored in temp, and decrement endIdx to move to the next character.

return new String(arr);: Convert the flipped string back to a string and return it.

Have a great day!
