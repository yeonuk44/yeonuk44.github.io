---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Question_Of_Dividing_A_And_B
title: Baekjun 1008, The question of dividing A and B
# title: Baekjun 1008, The question of dividing A and B
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
date: 2024-09-18 09:00:00 +0900
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

## Baekjun No. 1008, this is an article about A/B problem (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

After receiving the two integers A and B, write a program that outputs A/B.

#### Input

A and B are given in the first line. (0 < A, B < 10)

#### Output

Output A/B on the first line.

If the absolute or relative error between the actual correct answer and the output value is less than 10-9, it is the correct answer.

### problem solving

```java
import java.util.Scanner;

class Main{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        double a = scan.nextDouble();
        double b = scan.nextDouble();
        scan.close();
        System.out.print(String.format("%.10f", a / b));
    }
}

```

#### Solution Description

I was able to solve the problem and think about the difference between float and double.

Java uses two basic data types, double and float, to represent floating-point numbers.

These two types differ in the range and precision of the values that can be stored, with different advantages and disadvantages.

##### Differences

###### Precision and storage range:

float:

- 32-bit (4 bytes) size
- having a significant number of approximately 7 digits
- The range of values that can be expressed is approximately ±1.4E-45 to ±3.4E+38

double:

- 64 bit (8 bytes) size
- Have a valid number of approximately 15 digits
- The range of values that can be expressed is approximately ±4.9E-324 to ±1.8E+308

###### Precision and calculation:

Double has twice the number of bits as float, which allows more valid numbers to be expressed, resulting in higher precision.

This is advantageous when high precision is required, such as scientific and financial calculations.

Floats use less memory and can be advantageous when some graphics applications or memory usage is important, although the precision is relatively low.

##### pros and cons

float:

- Advantage: It is advantageous in environments with large arrays or memory constraints due to low memory usage. It can provide better performance in some graphics programming.
- Disadvantage: It can be inaccurate when dealing with a large number of valid numbers due to low precision. More errors can occur in calculations.

double:

- Advantage: The precision is high and can accurately handle many valid numbers. This is the default floating point type, so you don't have to specify an explicit type.
- Cons: Memory usage is twice as high as float.
  Some performance sensitive applications may be slower.

### Conclusion

For example, in graphical applications, performance can be optimized using float, but in financial calculations, it is important to maintain high precision using double.

When memory constraints are not large and precision is important: use double

When memory usage should be minimized, and precision is relatively less important: use float

Thank you!
