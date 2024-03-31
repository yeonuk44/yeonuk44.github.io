---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Route_And_Traffic_Control
title: 경로, 트래픽 제어에 대하여
# title: About route and traffic control
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
date: 2024-03-31 09:00:00 +0900
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

## 네트워크 구축에 대하여 알아본 글입니다.

오늘은 네트워크 구축에 대해 알아보겠습니다.

네트워크는 컴퓨터와 다른 장치들이 서로 연결되어 정보를 주고받을 수 있는 시스템입니다.

네트워크를 구축할 때는 여러 가지 설치 구조와 분류, 표준, 그리고 통신 기술에 대해 알아야 합니다.

이제 하나씩 살펴보도록 하겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 네트워크 설치 구조:

- 성형: 컴퓨터들이 원형으로 연결된 형태로, 한 컴퓨터가 다른 컴퓨터로 바로 연결됩니다.
- 링형: 컴퓨터들이 링 모양으로 연결되어 있으며, 각 컴퓨터는 양 옆 컴퓨터와 직접 연결됩니다.
- 버스형: 컴퓨터들이 한 줄로 연결되어 있으며, 모든 컴퓨터가 같은 통신 매체를 공유합니다.
- 계층형: 여러 개의 작은 네트워크가 계층적으로 구성되어 있으며, 상위 계층에서는 라우터를 사용하여 하위 계층과 통신합니다.
- 망형: 여러 개의 컴퓨터들이 복잡하게 연결되어 있는 형태로, 여러 경로를 통해 통신이 가능합니다.

### 네트워크 분류:

- LAN(Local Area Network): 작은 지리적 범위에서 사용되는 네트워크로, 옥내나 건물 내부 등 한정된 공간에서 사용됩니다.
- WAN(Wide Area Network): 넓은 지리적 범위를 커버하는 네트워크로, 인터넷과 같은 대규모 네트워크에 사용됩니다.

### LAN의 표준안(IEEE 802.x):

LAN은 IEEE(전기 및 전자 기술자 협회)에서 표준화된 규격을 따릅니다.

특히, LAN의 표준안은 IEEE 802.x 시리즈로 알려져 있습니다.

x는 다양한 버전을 의미하며, 각 버전은 특정 기술이나 통신 방식에 대한 규격을 정의합니다.

### 802.11의 버전:

802.11은 무선 LAN(WLAN)에 대한 표준을 정의하는 IEEE 802.x 시리즈 중 하나입니다.

802.11은 초기에는 2Mbps의 속도를 제공하는 무선 통신 기술이었지만, 점차 발전하여 다양한 버전이 등장했습니다.

예를 들어, 802.11b, 802.11g, 802.11n, 802.11ac 등이 있으며, 각 버전마다 속도와 호환성 등이 다를 수 있습니다.

### CSMA/CD와 CSMA/CA:

CSMA/CD(Carrier Sense Multiple Access with Collision Detection)는 이더넷과 같은 유선 네트워크에서 충돌을 감지하고 처리하는 방식입니다.

충돌이 발생하면 일정 시간 동안 대기한 후 재전송을 시도합니다.

CSMA/CA(Carrier Sense Multiple Access with Collision Avoidance)는 무선 네트워크에서 충돌을 예방하기 위한 방식입니다.

데이터를 전송하기 전에 다른 기기가 사용 중인지 확인하고 충돌을 최소화하기 위해 전송을 조절합니다.

## 마치며

이상으로 네트워크 구축에 대한 블로그 형식의 글을 작성해보았습니다.

네트워크 설치 구조와 분류, LAN의 표준, 그리고 무선 통신 기술에 대해 간략히 알아보았습니다.
