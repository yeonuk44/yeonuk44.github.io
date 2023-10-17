---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Calculate_Simple_Expression
title: Calculate a simple expression (with.Java)
# title: Calculate a simple expression (with.Java)
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
date: 2023-10-16 09:00:00 +0900
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

### In this article, we learned about calculating simple expressions.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

The string binomial is given as a parameter.

binomial is a binomial of the form "a op b", where a and b are non-negative integers, and op is one of '+', '-', or '\*'.

Write a solution function that returns an integer that computes the given expression.

##### Example input and output

binomial: "43 + 12"

result: 55

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int solution(String binomial) {
        String[] parts = binomial.split(" ");

        int a = Integer.parseInt(parts[0]);
        int b = Integer.parseInt(parts[2]);

        String op = parts[1];

        int result = 0;
        switch (op) {
            case "+":
                result = a + b;
                break;
            case "-":
                result = a - b;
                break;
            case "*":
                result = a * b;
                break;
        }

        return result;
    }
}
```

##### Solution

String[] parts = binomial.split(" ");: Splits the given binomial string based on whitespace and stores it in the parts array. This allows us to separate the operands and operators that are components of the binomial.

int a = Integer.parseInt(parts[0]); and int b = Integer.parseInt(parts[2]);: convert the first and third elements of the parts array to integers and store them in the operands a and b. This extracts the numeric part of the binomial.

String op = parts[1];: Stores the second element of the parts array in the operator string op. This operator will be one of "+", "-", or "\*".

int result = 0;: Initialize the variable result to store the result value.

switch (op) { ... }: Performs an operation using the switch statement based on the value of op.

case "+": : Performs an addition operation and stores the result in result.

case "-": : Performs a subtraction operation and stores the result in result.

case "\*": : Performs a multiplication operation and stores the result in result.

return result;: Returns the calculated result.
