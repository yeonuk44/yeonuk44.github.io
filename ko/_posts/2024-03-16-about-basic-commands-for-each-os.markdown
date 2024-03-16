---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Basic_Commands_For_Each_OS
title: 운영체제 별 기본 명령에 대하여
# title: About basic commands for each operating system
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
date: 2024-03-16 09:00:00 +0900
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

## 스케줄링 알고리즘과 동작 원리에 대하여 알아본 글입니다.

이번 글은 정보처리기사를 준비하며 이번에는 주요 스케줄링 알고리즘에 대해 알아보고자 합니다.

스케줄링 알고리즘은 운영체제에서 프로세스들의 실행 순서를 결정하는 중요한 역할을 합니다.

다양한 스케줄링 알고리즘이 개발되었는데, 함께 알아보도록 하겠습니다.

{:data-align="center"}

<!-- outline-end -->

### FCFS(First-Come, First-Served)

FCFS 알고리즘은 가장 간단한 스케줄링 알고리즘으로, 먼저 도착한 프로세스를 먼저 실행하는 방식입니다.

프로세스의 도착 순서에 따라 실행 순서가 결정되기 때문에 비선점형 스케줄링 알고리즘입니다.

하지만 실행 시간이 긴 프로세스가 먼저 도착하면, 뒤에 도착한 짧은 실행 시간을 가진 프로세스들이 오래 기다려야 하는 단점이 있습니다.

### SJF(Shortest Job First)

SJF 알고리즘은 실행 시간이 가장 짧은 프로세스를 우선적으로 실행하는 방식입니다.

실행 시간을 예측하여 실행 시간이 가장 짧은 프로세스를 먼저 실행하기 때문에 최소 대기 시간을 가질 수 있습니다.

하지만 실행 시간을 정확히 예측하기 어렵고, 실행 시간이 긴 프로세스가 무한히 대기할 수 있는 "기아 현상"이 발생할 수 있습니다.

### 우선순위 기반 스케줄링

우선순위 기반 스케줄링 알고리즘은 각 프로세스에 우선순위를 할당하고, 우선순위가 가장 높은 프로세스를 먼저 실행하는 방식입니다.

우선순위는 정수로 표현되며, 작은 숫자가 높은 우선순위를 가집니다.

이 알고리즘은 선점형과 비선점형으로 나뉘며, 우선순위가 변경될 수 있는 "동적 우선순위" 기반 알고리즘도 있습니다.

### Round Robin

Round Robin 알고리즘은 시분할 시스템에서 사용되는 대표적인 스케줄링 알고리즘입니다.

각 프로세스는 동일한 시간 할당인 "타임 슬라이스"를 가지고 순환적으로 실행됩니다.

타임 슬라이스가 지나면 실행 중이던 프로세스는 대기 상태로 이동하고, 다음 순서의 프로세스가 실행됩니다.

이를 통해 다중 프로그래밍 환경에서 공정한 실행 시간을 보장할 수 있습니다.

## 마치며

스케줄링 알고리즘은 프로세스들의 실행 순서를 결정하는 중요한 역할을 합니다.

각 알고리즘은 자체적인 장단점을 가지고 있으며, 운영체제의 목표에 따라 적절한 알고리즘을 선택해야 합니다.

이를 통해 시스템의 성능과 응답 시간을 최적화할 수 있습니다.

감사합니다.
