---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Deadlocks_And_Resolution_Techniques
title: About deadlocks and resolution techniques
# title: About deadlocks and resolution techniques
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Network
# multiple tag entries are possible
tags: [network]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-04-01 09:00:00 +0900
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

## 교착상태와 해결 기법에 대하여 알아본 글입니다.

안녕하세요! 오늘부터는 글의 생기를 불어넣기 위해 매일 조금씩 글의 주제와 상관없는 TMI를 넣어볼까합니다.

**오늘의 TMI**

오늘은 저의 26번째 생일입니다. 사실 이것저것 많은 것을 했는데 이 경험들이 제 인생에 도움이 될지 몰라 잠시 생각에 잠겼네요.. 지금은 아무것도 하지 않으면 변하지 않는다는 생각으로 꾸준히 계속 할 생각입니다! 여러분도 의미를 떠나 꾸준히 하고 있는 행동이 있나요? 언제가 될지는 모르지만 인생에 도움이 될 것이라고 생각합니다! 응원하겠습니다!

돌아와서 이번에는 컴퓨터 시스템에서 발생할 수 있는 교착상태에 대해 알아보고, 이를 해결하기 위한 기법들에 대해 살펴보겠습니다.

교착상태는 시스템 자원을 요구하며 동시에 점유하고 있는 프로세스들이 서로 필요한 자원을 기다리며 무한히 대기하는 상황을 말합니다.

이러한 상황은 시스템의 작동을 멈추게 할 수 있으므로 중요한 개념입니다.

지금부터 자세히 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 경로 제어의 개요

경로 제어는 패킷이 네트워크를 통해 전달될 때 어떤 경로를 따라야 하는지 결정하는 과정입니다.

이를 통해 패킷은 최적의 경로를 통해 목적지로 전송되며, 네트워크의 효율성과 성능을 향상시킵니다.

경로 제어는 라우팅 프로토콜을 사용하여 경로 정보를 교환하고, 경로 선택 알고리즘을 통해 최적 경로를 결정합니다.

### 경로 제어 프로토콜

경로 제어 프로토콜은 네트워크 장비 간에 경로 정보를 교환하기 위한 프로토콜입니다.

대표적으로 사용되는 경로 제어 프로토콜로는 OSPF (Open Shortest Path First), BGP (Border Gateway Protocol), RIP (Routing Information Protocol) 등이 있습니다.

이들 프로토콜은 각각의 특징과 용도에 따라 다양한 상황에서 경로 제어를 수행합니다.

### 트래픽 제어

트래픽 제어는 네트워크에서 발생하는 데이터 흐름을 제어하는 기술입니다.

네트워크에는 다양한 트래픽이 동시에 발생할 수 있으며, 효율적인 트래픽 제어는 네트워크 성능과 안정성을 유지하는 데 중요합니다.

트래픽 제어는 트래픽의 우선순위 설정, 대역폭 할당, 혼잡 제어 등을 포함합니다.

### 흐름 제어

흐름 제어는 송신 측과 수신 측 간의 데이터 전송 속도 조절을 위한 기술입니다.

데이터 송신 측은 수신 측의 처리 속도에 맞춰 데이터를 전송하여 혼잡을 방지하고, 수신 측은 송신 측에게 데이터를 처리할 시간을 알려주어 데이터의 과다 전송을 막습니다.

이를 통해 네트워크의 효율성을 향상시키고 데이터 손실을 방지할 수 있습니다.

### 폭주 제어

폭주 제어는 네트워크에 대한 과도한 요청이 발생하여 네트워크 자원이 과부하되는 현상을 방지하는 기술입니다.

이를 위해 트래픽 모니터링, 트래픽 필터링, 제한된 대역폭 할당 등의 방법을 사용하여 네트워크 자원의 효율적인 사용을 도모합니다.

### 교착상태 방지

교착상태는 네트워크에서 발생할 수 있는 상태로, 각 장치가 서로의 자원을 기다리며 무한히 대기하는 상황을 말합니다.

교착상태는 네트워크의 성능을 저하시키고, 전체 시스템의 동작을 멈추게 할 수 있습니다.

이를 방지하기 위해 교착상태 검출 및 복구 알고리즘을 사용하여 문제를 해결하고, 자원 할당과 해제를 적절히 조절합니다.

## 마치며

경로 제어와 트래픽 제어는 네트워크의 효율성과 안정성을 위한 핵심 개념입니다.

경로 제어는 최적 경로를 결정하여 패킷의 효율적인 전달을 도모하며, 트래픽 제어는 데이터 흐름을 조절하여 네트워크 성능을 향상시킵니다.

또한, 흐름 제어와 폭주 제어를 통해 데이터 전송과 네트워크 자원의 효율적인 사용을 지원하며, 교착상태 방지를 통해 네트워크의 안정성을 유지합니다.

이러한 개념들을 적절히 활용하여 네트워크 운영을 최적화하는 것이 중요합니다.
