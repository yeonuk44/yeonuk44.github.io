---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Concepts_And_Features_Of_Operating_Systems
title: UNIX, Linux, macOS 운영체제의 개념과 특징
# title: Concepts and features of UNIX, Linux, and macOS operating systems
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
date: 2024-03-14 09:00:00 +0900
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

## 기억장치 관리 개요, 구현 기법, 페이지 교체 알고리즘에 대하여 알아본 글입니다.

이번 글은 정보처리기사를 준비하며 이번에는 기억장치 관리에 대해 알아보고자 합니다.

기억장치 관리는 운영체제에서 중요한 역할을 담당하는 부분으로, 프로그램이 메모리에 올라가는 방식과 메모리 공간의 효율적인 활용을 위해 다양한 기법과 알고리즘이 사용됩니다.

함께 알아보도록 하겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 기억장치 관리 개요

기억장치 관리는 프로그램이 실행될 때 필요한 데이터와 명령어를 저장하고, 실행에 필요한 메모리 공간을 할당하는 역할을 합니다.

이를 효율적으로 관리하기 위해 다음과 같은 목표를 가지고 있습니다.

- 주소 공간 할당: 프로그램이 메모리에 올라갈 때 적절한 주소 공간을 할당하여 충돌이나 오버플로우를 방지합니다.
- 메모리 보호: 다른 프로그램이나 운영체제의 메모리 영역에 접근하지 못하도록 보호합니다.
- 메모리 공간의 효율적인 활용: 사용하지 않는 메모리 공간을 최소화하고, 다중 프로그래밍 환경에서 여러 프로세스가 동시에 실행될 수 있도록 합니다.

### 기억장치 관리 구현 기법

기억장치 관리는 다양한 구현 기법을 사용하여 메모리를 관리합니다. 주요 구현 기법으로는 다음과 같은 것들이 있습니다.

- 단일 고정 분할 할당: 메모리를 여러 개의 고정된 크기로 분할하고, 프로세스에게 할당합니다. 각 분할은 하나의 프로세스만 사용할 수 있으며, 다른 프로세스는 사용하지 못합니다.
- 가변 분할 할당: 메모리를 동적으로 분할하여 프로세스에게 할당합니다. 프로세스의 크기에 따라 필요한 만큼의 메모리 공간을 할당하고 해제할 수 있습니다.
- 페이징: 메모리를 고정된 크기의 페이지로 분할하고, 프로세스는 페이지 단위로 할당됩니다. 이를 통해 외부 단편화 문제를 해결할 수 있습니다.
- 세그멘테이션: 메모리를 논리적인 단위인 세그먼트로 분할하고, 프로세스는 세그먼트 단위로 할당됩니다. 세그먼트는 프로그램의 논리적인 부분으로, 코드, 데이터, 스택 등으로 구성됩니다.

### 페이지 교체 알고리즘

페이징 기법에서는 메모리에 모든 페이지를 올릴 수 없으므로, 필요한 페이지만 올리고 필요 없는 페이지는 보조 기억장치에 저장합니다.

페이지 부재가 발생하면 페이지 교체 알고리즘이 사용되어야 합니다.

주요 페이지 교체 알고리즘은 다음과 같습니다.

- FIFO(First-In, First-Out): 가장 먼저 들어온 페이지를 교체합니다.
- LRU(Least Recently Used): 가장 오랫동안 참조되지 않은 페이지를 교체합니다.
- LFU(Least Frequently Used): 가장 적게 참조된 페이지를 교체합니다.
- OPT(Optimal): 미래에 가장 오랫동안 사용되지 않을 페이지를 교체합니다. 이는 이론적으로 최적의 알고리즘이지만 실제로 구현하기 어렵습니다.

## 마치며

기억장치 관리는 운영체제의 핵심 기능 중 하나로, 프로그램의 실행 속도와 효율성에 큰 영향을 미칩니다.

이를 효과적으로 관리하는 것은 시스템의 안정성과 성능을 향상시키는 데 도움이 됩니다.

감사합니다.
