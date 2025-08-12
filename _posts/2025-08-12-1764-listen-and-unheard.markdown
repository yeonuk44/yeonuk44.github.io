---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-1764-listen-and-unheard
title: Baekjun, 1764, Listen and Unheard (with.Java)
# title: Baekjun, 1764, "With. Java"
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
date: 2025-08-12 09:00:00 +0900
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

## Baekjun No. 1764, this is an article about "with.Java."

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Write a program in which the Jinyoung Kim obtains a list of people who have not heard and who have not heard, when given a list of people who have not reported.

#### Input

In the first line, the number N of people who have not heard and the number M of people who have not reported are given.

Next, the names of those who have not heard from the second line and those who have not heard from the N+2 line are given in order.

The name consists of only lowercase alphabetic characters with no spaces, and is no more than 20. N and M are natural numbers no more than 500,000.

There are no overlapping names on the list of people who haven't heard of it, and the same goes for the list of people who haven't reported it.

#### Output

Print out the number of nibbles and their lists in dictionary order.

### Problem Solving

```java
import java.util.*;
import java.io.*;

class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());
        HashSet<String> N = new HashSet<>();
        ArrayList<String> answer = new ArrayList<>();
        int N_len = Integer.valueOf(st.nextToken());
        int M = Integer.valueOf(st.nextToken());
        for(int i = 0; i < N_len; i++){
            N.add(br.readLine());
        }
        for(int i = 0; i < M; i++){
            String temp = br.readLine();
            if(N.contains(temp)){
                answer.add(temp);
            }
        }
        int answer_len = answer.size();
        System.out.println(answer_len);
        Collections.sort(answer);
        for(int i = 0; i < answer_len; i++){
            System.out.println(answer.get(i));
        }
    }
}
```

#### Solution Description

This code is a program that finds and outputs strings that exist in common in two lists.

Find common elements in the given two lists first, then sort them in dictionary order and output them.

The program first processes the input using HashSet and ArrayList.

Save the string entered in the first list to HashSet.

Since HashSet uses hashmaps internally to store data, the contain() method of checking whether a particular element exists in a set has the time complexity of O(1) on average.

This is very efficient, and provides performance benefits, especially when the number of elements is high.

Then, read each element in the second list sequentially, and verify that it exists in the HashSet.

If present, add this element to the ArrayList.

ArrayList stores data sequentially, and contain() methods that verify that certain elements are included in the list are searched internally using indexOf(), so they have the time complexity of O(n).

In this code, we used ArrayList to collect and output duplicate elements, which is an appropriate choice for filtering elements using HashSet and then outputting sorted results.

Finally, the common elements stored in the ArrayList are sorted in dictionary order through Collections.sort().

Outputs the number of common elements before outputting the sorted results, and then outputs each element in order.

Initially, it was accessible using ArrayList to find redundant elements, but in this case, it was inefficient due to its increased time complexity.

By using HashSet, we have been able to significantly improve our efficiency, which is an important optimization, especially when the size of the input data is large.
