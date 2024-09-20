---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Oven_Clock
title: Baekjun no. 2525, oven clock (with.Java)
# title: Baekjun no. 2525, oven clock (with.Java)
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
date: 2024-09-20 09:00:00 +0900
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

## This is what we learned about Baekjun 2525 oven clock (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

KOI Electronics is trying to develop an AI oven that makes healthy and delicious grilled smoked duck dishes simple.

The way to use an AI oven is to put the right amount of duck-smoked material into the AI oven.

Then, the artificial intelligence oven automatically calculates the time when the oven is finished in minutes.

Also, on the front of KOI Electronics' AI oven is a digital clock that tells the user when grilled smoked duck cooking ends.

Write a program to calculate the time when the oven is finished, given the time to start the grilled smoked duck and the time required to bake the oven in minutes.

#### Input

The first line shows the current time.

The current time is given in order with time A (0≤A≤23) and minute B (0≤B≤59) as integers in between.

The second line is given in minutes the time C (0 ≤ C ≤ 1,000) required to cook.

#### Output

The time and minute of the time ending in the first line are output with a space between them.

(However, poetry is an integer from 0 to 23 and minutes is an integer from 0 to 59.

The digital clock will be 0:0 after one minute from 23:59.)

### problem solving

```java
import java.util.Scanner;

class Main{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        int hour = scan.nextInt();
        int minute = scan.nextInt();
        int working_time = scan.nextInt();

        hour += (minute + working_time) / 60;
        hour %= 24;
        minute = (minute + working_time) % 60;

        System.out.print(hour + " " + minute);
    }
}
```

#### Solution Description

Create a scanner object to prepare to receive input from the user.

Use the scan.nextInt() method to receive hour, minute, and working_time.

Divide the sum of the current minute and working_time by 60 to add to the hour.

If the calculated hour is more than 24, update it to the remaining value divided by 24 and keep it in 24-hour format.

Divide the sum of the current minute and working_time by 60 and update the remaining value to the new minute.

Outputs the calculated time and minutes.

Thank you!
