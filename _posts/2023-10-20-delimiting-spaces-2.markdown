---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Delimiting_Spaces_2
title: Delimiting Spaces 2 (with.Java)
# title: Delimiting Spaces 2 (with.Java)
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
date: 2023-10-20 09:00:00 +0900
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

### This is the second installment of our series on Space Separators.

We're going to learn about it by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Write a solution function that, given a string my_string with words separated by at least one space as a parameter, returns an array of strings containing the words in my_string in order from front to back.

##### Example input and output

| my_string       | result               |
| --------------- | -------------------- |
| " i love you"   | ["i", "love", "you"] |
| " programmers " | ["programmers"]      |

In Example 1, my_string is " i love you" and when we split the word based on spaces, we have 3 words: "i", "love", and "you".

Therefore, we return ["i", "love", "you"].

In example 2, my_string is " programmers", which has only one word, "programmers".

Therefore, return ["programmers"].

#### My solution to the problem

```java
import java.util.*;

class Solution {
    public String[] solution(String my_string) {
        String[] answer = my_string.split(" ");
        List<String> list = new ArrayList<>(Arrays.asList(answer));
        list.removeAll(Arrays.asList(""));
        return list.toArray(new String[0]);
    }
}

```

##### solution description

public String[] solution(String my_string): A function that takes the string my_string as input and solves the problem. Returns an array of strings as the return value.

String[] answer = my_string.split(" ");: code that takes the given string my_string, splits it based on whitespace, and creates a string array answer containing the words.

List<String> list = new ArrayList<>(Arrays.asList(answer));: Converts the array answer created above into a list and stores it in the list variable. This prepares us to manipulate the list and add/remove elements.

list.removeAll(Arrays.asList(""));: This code removes all empty strings from the list. Create a list containing empty strings using Arrays.asList("") and remove all elements belonging to this list from the list list.

return list.toArray(new String[0]);: This code converts the elements stored in the list list to an array of Strings and returns them. Here, new String[0] is responsible for creating a new String array of size 0. This array will be copied and contain the elements stored in the list list.

As a result, the code performs the task of separating the given string my_string by whitespace, removing the empty string, and returning the remaining words as an array of Strings.

While writing the code, I thought that if I set the initial size of the array to 0, no elements would be inserted into the array, but it worked as intended.

I'm also attaching what I realized.

The reason the code works as intended, even though you specify an initial size of 0 for the array, is because of the way Java works with arrays.

When an array is sized to zero, it doesn't actually create an array at all, but rather an array object of size zero.

This array object doesn't have space to store any actual elements, but the array object itself will exist.

In Java, arrays have a fixed size, so you must specify the size of the array when you create it.

So new String[0] creates an array object of size 0, which doesn't have space to store elements, but the array object itself will exist.

And the code list.toArray(new String[0]) returns this array object with the elements in it, which signals that we need a new array to hold the elements.

Inside Java, this array object is copied to a new size and filled with elements.

So even though you create an array object with an initial size of 0, when you return it with the elements in the list.toArray(new String[0]) code, a new resized array is actually created and filled with the elements.
