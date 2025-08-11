---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-9250-string-set-successful
title: Baekjun 9250, string set successful (with.Java)
# title: Baekjun 9250, string set successful (with.Java)
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
date: 2025-08-11 09:00:00 +0900
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

## Baekjun No. 9250, about the string set success (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

A set S consisting of a total of N strings is given.

Write a program to find out how many of the M strings given as inputs are in set S.

#### Input

The number of strings N and M (1≤N≤10,000 and 1≤M≤10,000) are given in the first line.

The next N lines are given the strings contained in the set S.

The next M lines are given strings to be examined.

The character string given as input consists only of lowercase alphabetic characters, and does not exceed 500 in length.

The sum S is not given the same string more than once.

#### Output

The first line outputs how many of the M strings are included in the set S.

### problem solving

```java
import java.util.*;
import java.io.*;

class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());
        int N = Integer.valueOf(st.nextToken());
        int M = Integer.valueOf(st.nextToken());
        HashSet<String> set = new HashSet<>();
        int count = 0;

        for(int i = 0; i < N; i++){
            set.add(br.readLine());
        }
        for(int i = 0; i < M; i++){
            String str = br.readLine();

            if(set.contains(str)){
                count++;
            }
        }

        System.out.print(count);
    }
}
```

#### Solution Description

This code is a program that finds the number of strings that exist in common in two lists.

Calculate and output how many elements overlap in the two lists given as inputs.

First, use Buffered Reader and String Tokenizer to process the input.

In the first line, enter the sizes of the two lists, N and M.

Then you create a HashSet to store the elements in the first list.

Because HashSet does not allow redundancy, redundant elements are automatically removed during this process.

As you read each element in the second list, make sure that it exists in the HashSet.

If present, increase the count to count the number of duplicate elements.

After all the comparisons are finished, you output a count to show the number of strings that exist in common in both lists as a result.

This method is efficient and can quickly identify redundant elements even if the two lists are large in size.
