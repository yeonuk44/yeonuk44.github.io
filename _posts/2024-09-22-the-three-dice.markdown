---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_the_three_dice
title: Baekjun 2480, 3 dice (with.Java)
# title: Baekjun 2480, 3 dice (with.Java)
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
date: 2024-09-22 09:00:00 +0900
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

## This is an article about Baekjun No. 2480 and three dice (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

There is a game in which you throw 3 dice with eyes from 1 to 6 and receive a prize according to the following rules.

If three of the same eyes come out, you will receive a prize of 10,000 won + (same eyes) × 1,000 won.

If only two of the same eyes come out, you will receive a prize of 1,000 won + (same eye) × 100 won.

If all of them have different eyes, they will receive a prize of KRW 100 (the biggest of them).

For example, if three eyes 3, 3, and 6 are given, the prize money is calculated as 1,000+3×100 and received 1,300 won.

In addition, if three eyes are given as two, two, and two, it is calculated as 10,000+2×1,000 and received 12,000 won.

If three eyes are given as 6, 2, and 5, the largest value is 6, so it is calculated as 6×100 and 600 won is received as a prize.

Write a program that calculates the prize money when you are given three dice eyes.

#### Input

Three eyes are given in the first row, each with a blank space between them.

#### Output

Print the prize money of the game on the first line.

### problem solving

```java
import java.util.Scanner;
class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int a = scan.nextInt();
        int b = scan.nextInt();
        int c = scan.nextInt();
        int answer = 0;

        if (a == b && b == c) {
            answer = 10000 + (a * 1000);
        }else if(a == b || a == c){
            answer = 1000 + (a * 100);
        }else if(b == c){
            answer = 1000 + (b * 100);
        }else{
            if(a >= b && a >= c){
                answer = a * 100;
            }else if(b >= a && b >= c){
                answer = b * 100;
            }else{
                answer = c * 100;
            }
        }
        System.out.print(answer);
    }
}
```

#### Solution Description

Initialize the variable to store the result by declaring intanswer = 0.

- If all three dice values are the same: if (a == b & b == c) Check through the conditional statement, and store the value 10000 + (a \_1000) in answer.
- If two dice are equal: store 1000 + (a \_ 100) values in answer if (a == b | | a == c) conditional statement if more than one a is equal. store 1000 + (b \* 100) values in answer if (b == c) conditional statement if b and c are equal.
- If all three dice values are different: Find the largest of the three numbers in the else block. Compare a, b, and c and store the largest value multiplied by 100 in answer.

This code is a program that calculates the results of a dice game.

It receives three dice values and calculates and outputs scores in cases where the three values are equal, the two values are equal, and the three values are all different.

Thank you!
