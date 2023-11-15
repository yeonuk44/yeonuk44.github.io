---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sum_Of_Two_Numbers
title: Sum of two numbers (with.Java)
# title: Sum of two numbers (with.Java)
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
date: 2023-11-14 09:00:00 +0900
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

### This is a post about the "sum of two numbers" problem.

We're going to learn about it by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

#### Problem

Write a solution function that returns the value of a + b as a string, given two integers greater than or equal to 0.

##### Example input and output

| a                      | b                       | result                  |
| ---------------------- | ----------------------- | ----------------------- | --- |
| "582"                  | "734"                   | "1316"                  |
| "18446744073709551615" | "287346502836570928366" | "305793246910280479981" |
| "0"                    | "0"                     | "0"                     | "0" |

My solution to the problem ####

```java
class Solution {
    public String solution(String a, String b) {
        String answer = "";
        int intA = Integer.parseInt(a);
        int intB = Integer.parseInt(b);
        int sum = intA + intB;
        answer = String.valueOf(sum);
        return answer;
    }
}
```

Explaining the solution to #####

Initially, you wrote code that converted to the Integer data type, added it, converted it back to a string, and returned it, but the 18446744073709551615 in Testcase 2 did not pass because the integer was too large.

I then solved the problem using long, which is twice the size of the Integer data type.

#### solved using longs

```java
class Solution {
    public String solution(String a, String b) {
        String answer = "";
        long longA = Long.parseLong(a);
        long longB = Long.parseLong(b);
        long sum = longA + longB;
        answer = String.valueOf(sum);
        return answer;
    }
}
```

However, even with the long data type, we were unable to pass 18446744073709551615 in Testcase 2.

It's too big a number.

So we used the BigInteger class to handle very large integer values.

#### Solving with BigInteger

```java
import java.math.BigInteger;

public class Solution {
    public String solution(String a, String b) {
        String answer = "";
        BigInteger bigA = new BigInteger(a);
        BigInteger bigB = new BigInteger(b);
        BigInteger sum = bigA.add(bigB);
        answer = sum.toString();
        return answer;
    }
}
```

The above code converts the two input strings to BigInteger objects and adds them using the add method.

It then uses the toString method to convert the result to a string and returns it.

This allows us to accurately handle very large integer values.
