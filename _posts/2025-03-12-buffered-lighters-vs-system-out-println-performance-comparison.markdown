---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-buffered-lighters-vs-system-out-println-performance-comparison
title: Buffered Lighters vs. System.out.println() Performance Comparison
# title: Buffered Lighters vs. System.out.println() Performance Comparison
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
date: 2025-03-12 09:00:00 +0900
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

## This article examines the performance comparison between BufferedWriter vs. System.out.println().

BufferedWriter and System.out.println(), the representative classes responsible for output in Java, work in different ways internally.

{:data-align="center"}

<!-- outline-end -->

### BufferedWriter

BufferedWriter stores the output data in a buffer and outputs it at once when it becomes a certain size or flush() is called.

This approach serves to optimize performance by combining multiple small output tasks into one large task.

#### Advantages

- High performance when outputting large amounts of data
- Save CPU resources by reducing unnecessary I/O calls

#### Disadvantages

- Output only occurs when flush() is called
- Outputting small amounts of data can lead to overhead

### System.out.println()

System.out.println() uses PrintStream internally to output data immediately.

However, since this PrintStream is buffered internally, it can also work faster than BufferedWriter in simple outputs.

#### Advantages

- Ready to output
- Fast output of small amounts of data

#### Disadvantages

- Repeated output of large amounts of data can degrade performance
- Performance optimization is not as automatic as BufferedWriter

### Conclusion

If the amount of output data is small, BufferedWriter may perform worse than System.out.println().

This is due to the unnecessary overhead of calling flush() without taking advantage of buffering.
