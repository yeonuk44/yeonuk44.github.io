---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Retrospective_And_Age_Of_Explanets
title: A short retrospective on 2023 and the age of exoplanets (with.Java)
# title: A short retrospective on 2023 and the age of exoplanets (with.Java)
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
date: 2023-12-31 09:00:00 +0900
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

## A brief retrospective

Here we are at the end of 2023, and it's been a year of exams, English certifications, and personal growth.

It's been a year that I've had a lot to look forward to and a lot to reflect on. I wish everyone who reads this article the best of luck for the upcoming 2024 without any regrets.

Currently, I am preparing for my Chinese certificate and chauffeur's license. If I have time, I'll try to make this blog not only about development but also about me as a person. lol

Always be happy!

## This article is about the "Age of Alien Planets" problem.

I'm going to share a retrospective on solving the problem, as well as other ways to solve it, and learn from it.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### The Problem

You are traveling in space, but your engine fails and you crash land on the planet PROGRAMMERS-962.

At immigration, you are asked to state your age, but on the planet PROGRAMMERS-962, ages are expressed in alphabetical order: a is 0, b is 1, c is 2, ..., j is 9.

For example, a 23-year-old is represented by CD and a 51-year-old by FB. Complete the solution function so that it returns the PROGRAMMER-962 expression age when age is given as a parameter.

#### Limitations

age is a natural number.

age ≤ 1,000

PROGRAMMERS-962 planets use only lowercase letters of the alphabet.

#### Example input and output

| age | result |
| --- | ------ |
| 23  | "cd"   |
| 51  | "fb"   |
| 100 | "baa"  |

My solution to the ### problem

```java
class Solution {
    public String solution(int age) {
        String answer = "";
        for (int i = 0; i < Integer.toString(age).length(); i++) {
            answer += (char) ((char) Integer.toString(age).charAt(i) + 49);
        }

    } return answer;
}
```

#### Solution

This code is a function that takes a given natural number age, maps each digit to an alphabet, and returns it as a string. Here is a brief explanation of the code

String answer = "";: Initialize an empty string answer to store the result.

for (int i = 0; i < Integer.toString(age).length(); i++) : Sets up a for loop that converts the given number age to a string, iterating over each digit of the string.

answer += (char)((char) Integer.toString(age).charAt(i) + 49);: converts the character of the current digit to an ASCII value, converts that value to a character plus 49, and adds it to answer.

The reason for adding 49 is that each digit plus 49 is the alphabet of the corresponding ASCII code. (0 plus 49 is 'a', 1 plus 49 is 'b', ..., 9 plus 49 is 'j')

return answer;: Returns the converted string.

The code is using a simple method of converting each digit to an alphabet.

For example, given 23, it would return "cd". The code is utilizing a loop to process the string and convert each digit.

Let's also take a quick look at Ascii code.

##### What is Ascii code?

ASCII code is a standard encoding scheme used to represent characters on computers.

ASCII stands for "American Standard Code for Information Interchange" and was first developed in the United States.

The ASCII code uses 7 bits to represent characters and contains 128 characters in total, from 0 to 127.

The code primarily contains the English alphabet, numbers, and special characters. Here's an example

Example ASCII code

Uppercase English letters: A-Z (65 through 90)

Lowercase English letters: A-Z (97 through 122)

Numbers: 0-9 (48 through 57)

Special characters: !, @, #, $, %, etc.

###### Summary

ASCII code is widely used as a standard for exchanging and representing characters between computers, and many programming languages are based on it.

ASCII code is also the basis for many different character encoding schemes, such as Extended ASCII and Unicode.
