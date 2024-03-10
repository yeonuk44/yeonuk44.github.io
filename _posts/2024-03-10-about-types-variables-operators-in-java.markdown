---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Types_Variables_Operators_In_Java
title: About types, variables, and operators in Java
# title: About types, variables, and operators in Java
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-03-10 09:00:00 +0900
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

## This is an article about types, variables, and operators in Java.

In this article, we will learn about basic data types, variables, and operators in Java programming in preparation for an information processing article.

{:data-align="center"}

<!-- outline-end -->

### Data Types

It is largely divided into primitive data types and reference data types.

**Basic data type**

- Integer type: byte, short, int, long
- Real number: float, double
- Character type: char
- Logical type: boolean

**Reference Data Type**

- Class
- Interface
- Array

### Variables

A variable represents a memory space that stores data.

In Java, when declaring a variable, you must specify the data type of that variable.

The data type of a variable determines the type and size of data that the variable can store.

For example, to store integers, use the 'int' data type, and to store characters, use the 'char' data type.

```java
int age = 20;
char gender = 'F';
```

### Operators

Java provides various operators to manipulate data.

- Arithmetic operators: +, -, \*, /, %, etc.
- Comparison operators: ==, !=, >, <, >=, <=, etc.
- Logical operators: &&, ||, ! etc.
- Assignment operators: =, +=, -=, \*=, /=, %=, etc.

For example, to calculate the sum of two numbers, use the '+' arithmetic operator, and to compare two values for equality, use the '==' comparison operator.

```java
int sum = 10 + 20; // Arithmetic operators
boolean isEqual = (sum == 30); // comparison operator
```

## Conclusion

We learned about data types, variables, and operators in Java.

These are fundamental components of Java programming, so you should have a solid understanding of them.
