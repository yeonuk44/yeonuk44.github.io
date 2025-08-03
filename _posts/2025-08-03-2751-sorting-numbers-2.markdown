---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-2751-sorting-numbers-2
title: Baekjun No. 2751, Sorting numbers 2 (with.Java)
# title: Baekjoon Problem 2751, Sorting Numbers 2 (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple categories is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test]
#thumbnailimageforpost
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2025-08-03 09:00:00 +0900
#seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

#optional
#please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
#please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# The image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on-site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

## This article explores Baekjoon Problem 2751, Sorting Numbers 2 (with Java).

We will learn by solving coding test problems, reflecting on previous problems, and exploring different solution methods.

Let's first look at the problem.

{:data-align="center"}

<!-- outline-end -->

### Problem

Given N numbers, write a program to sort them in ascending order.

#### Input

The first line contains the number N (1 ≤ N ≤ 1,000,000).

The second and subsequent N lines contain numbers.

These numbers are integers whose absolute values are less than or equal to 1,000,000.

Numbers cannot be duplicated.

#### Output

Sort the results in ascending order on the first N lines, one per line.

### Problem Solution

```java
import java.util.PriorityQueue;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.BufferedWriter;
import java.io.OutputStreamWriter;
import java.io.IOException;

class Main{
    public static void main(String[] args) throws IOException {
    PriorityQueue<Integer> queue = new PriorityQueue<>();
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
    int len = Integer.valueOf(br.readLine().trim());

    for(int i = 0; i < len; i++){
        queue.offer(Integer.valueOf(br.readLine().trim()));
    }
    br.close();

    while(!queue.isEmpty()){
        bw.write(String.valueOf(queue.poll()));
        if(!queue.isEmpty()){
            bw.newLine();
        }
    }
    bw.flush();
    bw.close();
    }
}
```

#### Solution Explanation

This code sorts the given numbers in ascending order and outputs them.

First, it uses a PriorityQueue to store integers.

It uses a BufferedReader to receive input, and a BufferedWriter to output them.

The first line of input contains the number of numbers, which is stored in the len variable.

Then, it loops through the input and adds each number to the queue.

After all numbers have been received, it retrieves each number from the PriorityQueue and outputs it using the BufferedWriter.

After each number is output, it adds a line break to format it correctly.

Finally, it flushes and closes the BufferedWriter to terminate the program.

This program provides a function to efficiently input, sort, and output numbers.

Thank you!
