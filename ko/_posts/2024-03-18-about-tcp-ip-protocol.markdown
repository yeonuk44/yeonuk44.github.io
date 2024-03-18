---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_TCP_IP_Protocol
title: TCP/IP 프로토콜에 대하여
# title: About TCP/IP protocol
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
date: 2024-03-18 09:00:00 +0900
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

## OSI 참조 모델에 대하여 알아본 글입니다.

이번 글은 정보처리기사를 준비하며 이번에는 OSI(Open Systems Interconnection) 참조 모델에 대해 알아보고자 합니다.

네트워크 통신의 구조를 이해하기 위한 이 모델은 전 세계적으로 널리 사용되고 있습니다.

함께 살펴보도록 하겠습니다.

{:data-align="center"}

<!-- outline-end -->

### OSI 참조 모델의 계층

**물리 계층 (Physical Layer)**

전기 신호나 비트 스트림으로 데이터를 전송합니다.

데이터 전송에 필요한 물리적인 연결과 전송 매체 등을 다룹니다.

**데이터 링크 계층 (Data Link Layer)**

데이터를 블록 단위로 나누고, 에러 검출 및 수정을 수행합니다.

물리 계층에서 전송된 데이터를 프레임 형태로 구성합니다.

### 네트워크 계층 (Network Layer)

여러 경로 중 가장 효율적인 경로를 선택하고, 패킷을 전송합니다.

IP 주소를 통해 목적지를 식별하고, 라우팅을 수행합니다.

**전송 계층 (Transport Layer)**

데이터의 신뢰성과 흐름 제어를 담당합니다.

데이터를 세그먼트로 분할하고, 에러 복구 및 재전송을 수행합니다.

### 세션 계층 (Session Layer)

통신 세션을 설정, 유지, 종료하는 역할을 합니다.

데이터의 동기화와 대화 제어를 담당합니다.

**표현 계층 (Presentation Layer)**

데이터의 포맷 변환, 암호화, 압축 등의 변환 작업을 수행합니다.

데이터를 응용 계층에서 이해할 수 있는 형식으로 변환합니다.

### 응용 계층 (Application Layer)

사용자와 네트워크 간의 인터페이스를 제공합니다.

사용자 애플리케이션에 서비스를 제공하고, 데이터의 최종 목적지입니다.

**OSI 참조 모델의 장점**

계층화된 구조로 인해 네트워크 통신의 각 단계를 이해하기 쉽습니다.

다른 벤더나 프로토콜 간의 호환성을 보장합니다.

특정 계층의 변경이 다른 계층에 미치는 영향을 예측할 수 있습니다.

표준화된 모델로써 네트워크 설계와 문제 해결에 유용합니다.

## 마치며

OSI 참조 모델은 네트워크 통신의 기본 개념을 이해하는 데 있어서 중요한 도구입니다.

각 계층의 역할과 기능을 이해하고, 이를 기반으로 네트워크 구성과 문제 해결에 접근해 보세요.
