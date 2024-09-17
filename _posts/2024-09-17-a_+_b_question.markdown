---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_a_+_b_question
title: Baekjun 1000, A+B question (with.Java)
# title: Baekjun 1000, A+B question (with.Java)
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
date: 2024-09-17 09:00:00 +0900
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

## This is an article about Baekjun no. 1000 A+B problem (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

After receiving the two integers A and B, write a program that outputs A+B.

#### Input

A and B are given in the first line. (0 < A, B < 10)

#### Output

Output A+B on the first line.

#### problem solving

It receives two integers from the user and outputs the sum.

To do this, use a scanner class to process the input and output the results.

### my solution to the problem

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner = new scanner (System.in ); // Create a scanner object to receive input
        inta = scan.nextInt(); // take the first integer and store it in variable a
        int b = scan.nextInt(); // take the second integer and store it in variable b
        System.out.print(a + b); // Output the sum of a and b
        scan.close(); // close the scanner object to release system resources
    }
}
```

#### Solution Description

We solved the problem and learned more about closing the scanner object.

If you do not close the scanner object, resources may not be released until the program is terminated.

This can lead to memory leaks, especially in long-running programs, which can waste system resources.

### Conclusion

Through this simple program, I learned how to take and process user input from Java.

Understanding how to use a scanner class to receive input, process it, and output results is fundamental to Java programming.

Also, don't forget to use scan.close() to properly release used system resources.

Thank you!
