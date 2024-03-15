---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Scheduling_Algorithms_And_Operating
title: About scheduling algorithms and operating principles
# title: About scheduling algorithms and operating principles
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: OS
# multiple tag entries are possible
tags: [os]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-03-15 09:00:00 +0900
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

## This is an article about scheduling algorithms and operating principles.

In this article, we are preparing an information processing article and will look into major scheduling algorithms.

Scheduling algorithms play an important role in determining the execution order of processes in an operating system.

Various scheduling algorithms have been developed, and we will take a look at them together.

{:data-align="center"}

<!-- outline-end -->

### First-Come, First-Served (FCFS)

The FCFS algorithm is the simplest scheduling algorithm and executes the process that arrives first.

It is a non-preemptive scheduling algorithm because the execution order is determined by the arrival order of processes.

However, if a process with a long execution time arrives first, processes with a short execution time that arrive later have to wait a long time.

### Shortest Job First (SJF)

The SJF algorithm prioritizes the process with the shortest execution time.

By predicting execution time, processes with the shortest execution time are executed first, allowing for minimal latency.

However, it is difficult to accurately predict execution time, and "starvation" may occur, where a process with a long execution time may wait indefinitely.

### Priority-based scheduling

A priority-based scheduling algorithm assigns a priority to each process and executes the process with the highest priority first.

Priority is expressed as an integer, with smaller numbers having higher priorities.

These algorithms are divided into preemptive and non-preemptive types, and there is also a "dynamic priority" based algorithm where the priority can be changed.

### Round Robin

The Round Robin algorithm is a representative scheduling algorithm used in time sharing systems.

Each process runs recursively with the same time allocation, or “time slice”.

After the time slice, the running process moves to the waiting state, and the next process in the order is executed.

This ensures fair execution times in multiprogramming environments.

## Conclusion

Scheduling algorithms play an important role in determining the execution order of processes.

Each algorithm has its own pros and cons, and the appropriate algorithm must be selected depending on the goals of the operating system.

This helps you optimize your system's performance and response time.

thank you
