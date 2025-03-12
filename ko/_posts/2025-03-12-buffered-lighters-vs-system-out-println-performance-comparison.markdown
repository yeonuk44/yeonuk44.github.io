---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-buffered-lighters-vs-system-out-println-performance-comparison
title: BufferedWriter vs System.out.println() 성능 비교
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

## BufferedWriter vs System.out.println() 성능 비교에 대하여 알아본 글입니다.

자바에서 출력을 담당하는 대표적인 클래스인 BufferedWriter와 System.out.println()은 내부적으로 서로 다른 방식으로 동작합니다.

{:data-align="center"}

<!-- outline-end -->

### BufferedWriter

BufferedWriter는 출력 데이터를 버퍼에 저장한 후, 일정 크기가 되거나 flush()가 호출될 때 한 번에 출력합니다.

이 방식은 여러 번의 작은 출력 작업을 한 번의 큰 작업으로 합쳐서 성능을 최적화하는 역할을 합니다.

#### 장점

- 많은 양의 데이터를 출력할 때 성능이 뛰어남
- 불필요한 I/O 호출을 줄여 CPU 자원을 절약

#### 단점

- flush()를 호출해야 출력이 됨
- 적은 양의 데이터를 출력할 경우, 오히려 오버헤드가 발생할 수도 있음

### System.out.println()

System.out.println()은 내부적으로 PrintStream을 사용하여 데이터를 즉시 출력합니다.

하지만 이 PrintStream도 내부적으로 버퍼링을 적용하고 있기 때문에, 간단한 출력에서는 BufferedWriter보다 빠르게 동작할 수도 있습니다.

#### 장점

- 즉각적인 출력 가능
- 적은 양의 데이터 출력 시 빠름

#### 단점

- 대량의 데이터를 반복해서 출력하면 성능 저하 발생 가능
- BufferedWriter처럼 성능 최적화가 자동으로 이루어지지 않음

### 결론

출력 데이터 양이 적을 경우 BufferedWriter를 사용하면 System.out.println()보다 성능이 떨어질 수 있습니다.

버퍼링의 장점을 거의 활용하지 못한채로 flush()를 호출하는 불필요한 오버헤드가 발생하기 때문입니다.
