---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Forward_Proxy_And_Reverse_Proxy
title: 포워드 프록시와 리버스 프록시에 대하여
# title: About Forward proxy and Reverse proxy
# post specific
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
date: 2024-01-10 09:00:00 +0900
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

## "포워드 프록시와 리버스 프록시"에 대하여

네트워크 공부를 하며 알게된 개념에 대해 정리한 글입니다.

컴퓨터 네트워크와 웹 보안은 현대 비즈니스 및 개인 활동에서 핵심적인 역할을 합니다.

이러한 분야에서 포워드 프록시와 리버스 프록시는 중요한 보안 도구로 사용됩니다.

이번 글에서는 포워드 프록시와 리버스 프록시가 무엇이며, 어떻게 네트워크 통신 보안에 기여하는지 살펴보겠습니다.

우선 포워드와 리버스 프록시에 대해 논하기 전에 프록시가 무엇인지부터 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 프록시(Proxy)란?

네트워크 통신에서 중개 역할을 하는 서버 또는 소프트웨어의 일반적인 개념입니다.

프록시는 클라이언트와 서버 사이에 위치하여 클라이언트의 요청을 받아 서버로 전달하고, 서버로부터의 응답을 클라이언트에게 반환합니다.

이러한 중개 역할을 통해 프록시는 다양한 목적으로 사용됩니다.

이제 포워드, 리버스 프록시에 대해 알아보겠습니다.

### 포워드 프록시 (Forward Proxy)의 개념

포워드 프록시는 클라이언트와 외부 서버 간의 중계 역할을 하는 서버입니다.

클라이언트가 외부 서버에 직접 연결하지 않고 포워드 프록시를 통해 연결합니다.

이런 중계 역할은 다양한 목적으로 사용됩니다.

#### 목적

- 보안 강화: 포워드 프록시는 클라이언트의 실제 IP 주소를 감추고 대신 프록시 서버의 IP 주소를 노출시킴으로써 익명성을 제공합니다. 이것은 클라이언트의 개인 정보와 위치 정보를 보호하는 데 도움이 됩니다.
- 캐싱: 포워드 프록시는 이전에 요청된 데이터의 복사본을 저장하고 동일한 요청이 다시 발생할 때 클라이언트 대신 저장된 데이터를 제공하여 대역폭을 절약하고 응답 시간을 단축시킵니다.
- 접근 제어: 조직 내에서 웹 사용을 관리하고 특정 웹 사이트에 대한 액세스를 제어하기 위해 사용될 수 있습니다.

### 리버스 프록시 (Reverse Proxy)의 개념

리버스 프록시는 외부 요청을 내부 서버로 중계하는 역할을 하는 서버입니다.

클라이언트는 리버스 프록시를 통해 내부 서버와 통신하며, 내부 서버는 클라이언트와 직접 통신하지 않습니다.

이러한 아키텍처는 다음과 같은 목적으로 사용됩니다.

#### 목적

- 보안 강화: 리버스 프록시는 내부 서버의 위치를 숨기고 클라이언트와 외부 서버 간의 통신을 제어합니다. 이는 내부 서버를 직접 노출하지 않고 외부 요청을 필터링하고 검증하는 데 사용됩니다.
- 로드 밸런싱: 리버스 프록시는 여러 내부 서버로 요청을 분배하여 부하를 분산시킵니다. 이로써 시스템의 성능을 향상시키고 가용성을 유지할 수 있습니다.
- SSL 암호화: 리버스 프록시는 SSL/TLS 암호화를 해독하고 내부 서버와의 안전한 통신을 가능하게 합니다.
- 캐싱: 리버스 프록시는 외부 요청에 대한 응답을 캐싱하여 동일한 요청에 대한 빠른 응답을 제공합니다.

### 결론

프로젝트의 역할과 목적에 따라 프록시의 위치를 결정하면 됩니다.
