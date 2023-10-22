---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Count_Between_x
title: Count between x (with.Java)
# title: Count between x (with.Java)
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
date: 2023-10-21 09:00:00 +0900
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

This is a post about the number between ### and x.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given a string myString.

Complete a solution function that, when myString is divided by the character "x", returns an array that stores the length of each of the divided strings in order.

##### Example input and output

If you divide the string by "x", you get ["o", "oo", "o", "", "o", ""].

If we create an array with the lengths of each, it is [1, 2, 1, 0, 1, 0], so we return [1, 2, 1, 0, 1, 0].

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public int[] solution(String myString) {
        int[] answer;
        char[] c = new char[myString.length()];
        ArrayList<Integer> flag = new ArrayList<Integer>();
        for(int i = 0; i < myString.length(); i++){
            if(myString.charAt(i) == 'x'){
                flag.add(i);
            }
        }

        if(flag.get(flag.size() - 1) == myString.length() - 1 || flag.get(0) == 0){
            answer = new int[flag.size() + 1];
        } else {
            answer = new int[flag.size()];
        }

        for(int i = 0; i < flag.size(); i++){
            System.out.println(flag.get(i));
            if(i == 0){
                answer[i] = flag.get(i);
            }else{
                answer[i] = flag.get(i) - flag.get(i-1) - 1;
            }
        }
        answer[answer.length - 1] = myString.length() - 1 - flag.get(flag.size() - 1);
        return answer;
    }
}
```

##### Solution Explained

Initially, I solved the test problem with the above code, but it didn't pass the other test cases. Here's my thought on why it didn't pass.

- Given a string myString, we need to split the string based on "x" and store the length of each substring.
- The code tries to find the position of the "x" and store it in the flag list, and calculate the length of each substring based on it. However, the position the code stores in the flag list represents the index of the "x", not the position of the "x" character. Therefore, when calculating the length of each substring, there will be a difference between the position of the "x" and the index, resulting in unexpected results.
- For example, in the string "oxooxoxoxxox", the position of "x" is [1, 3, 5, 6, 8], but the code stores the index of "x", [1, 2, 4, 5, 7], in the flag list, not this position.
- This results in an unexpected result like [1, 2, 1, 0, 2, 0] because when calculating the length of the substring, it looks for the difference between the indices.

This means that to fix the problem, you need to divide the string based on "x" and calculate the length of each substring, not the position of "x".

Below is the self-diagnosed and newly written code.

###### Newly written code

```java
import java.util.*;

class Solution {
    public int[] solution(String myString) {
        ArrayList<Integer> lengths = new ArrayList<Integer>();
        int length = 0;

        for (int i = 0; i < myString.length(); i++) {
            if (myString.charAt(i) == 'x') {
                lengths.add(length);
                length = 0;
            } else {
                length++;
            }
        }

        lengths.add(length); // add the length of the last substring

        int[] answer = new int[lengths.size()];
        for (int i = 0; i < lengths.size(); i++) {
            answer[i] = lengths.get(i);
        }

    } return answer;
}
```

###### Modified code snippet

ArrayList<Integer> lengths = new ArrayList<Integer>();: Create a list lengths to store the length of the substring.

int length = 0;: Initialize the variable length to store the length of the current substring.

for (int i = 0; i < myString.length(); i++) { ... }: Starts a loop that traverses the given string, myString, character by character.

if (myString.charAt(i) == 'x') { ... }: Checks to see if the current character is "x". If it is "x", add the length of the substring up to this point to the lengths list and initialize the length variable to 0.

If we encounter a non-"x" string, we increment the length value by 1.

Traverse the string through the loop, correctly calculating the length of the substring relative to "x" and storing it in the lengths list.

lengths.add(length);: Add the length of the last substring to the lengths list.

int[] answer = new int[lengths.size()];: Create the result array answer based on the lengths list with a fixed length.

for (int i = 0; i < lengths.size(); i++) { ... }: Copy the length of the substring stored in the lengths list into the answer array.

The function terminates and returns the answer array. This array stores the length of each substring, divided by "x", in order.
