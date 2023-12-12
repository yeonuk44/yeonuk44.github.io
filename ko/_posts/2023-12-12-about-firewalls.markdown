---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Firewalls
title: 방화벽에 대하여
# title: About firewalls
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
date: 2023-12-12 09:00:00 +0900
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

## "방화벽에 대하여" 문제에 대하여 알아본 글입니다.

네트워크 공부를 하며 알게된 개념에 대해 정리한 글입니다.

{:data-align="center"}

<!-- outline-end -->

### 개념

방화벽 (Firewall)은 컴퓨터 네트워크에서 네트워크 트래픽을 감시하고 제어하여 보안을 유지하는 데 사용되는 장치나 소프트웨어입니다.

방화벽은 불법한 액세스, 해킹, 바이러스, 스파이웨어 및 다른 악성 활동으로부터 네트워크와 컴퓨터 시스템을 보호하는 역할을 합니다.

### 역할

1. 패킷 필터링: 방화벽은 데이터 패킷 (네트워크에서 전송되는 작은 데이터 조각)을 검사하여 수신된 데이터가 허용되는 규칙에 따라 어느 방향으로 허용 또는 차단되어야 하는지 결정합니다. 이러한 규칙은 포트 번호, IP 주소, 프로토콜 등과 관련이 있습니다.
2. 상태 추적: 일부 방화벽은 네트워크 연결의 상태를 추적하여 데이터 패킷이 허용된 연결인지 확인합니다. 이것은 보안을 더 강화하는 데 사용됩니다.
3. 애플리케이션 계층 검사: 고급 방화벽은 데이터 패킷 내용을 분석하여 특정 애플리케이션의 행동을 감지하고 차단할 수 있습니다.
4. 악성 코드 및 스파이웨어 차단: 방화벽은 바이러스, 웜, 트로이 목마, 스파이웨어 및 기타 악성 코드를 감지하고 차단할 수 있습니다.
5. 가상 사설망 (VPN) 지원: 일부 방화벽은 안전한 원격 액세스를 위해 VPN 연결을 지원합니다.
6. 보안 로깅 및 모니터링: 방화벽은 네트워크 활동을 로그에 기록하고, 보안 관리자가 네트워크에서 어떤 일이 일어나고 있는지 모니터링할 수 있도록 합니다.

방화벽으로 막지 못하는 공격도 있습니다. 자세히 알아보겠습니다.

#### 방화벽으로 막지 못하는 공격의 원리

방화벽은 주로 네트워크 트래픽의 패킷 헤더 (패킷의 출발지, 목적지 IP 주소, 포트 번호 등)를 검사하여 트래픽을 필터링하고 허용 또는 차단합니다.

그러나 방화벽은 일반적으로 통신 데이터의 내용 자체를 깊게 분석하지는 않습니다.

이로 인해 다음과 같은 경우에서 공격을 막지 못할 수 있습니다.

#### 막지못하는 공격의 종류

1. 암호화된 트래픽: 방화벽은 트래픽의 내용을 이해하지 못하므로 암호화된 트래픽 (예: HTTPS)을 통과시킵니다. 암호화된 트래픽 내부의 데이터는 방화벽에서는 복호화되지 않으며, 공격자가 암호화된 통신을 통해 악의적인 활동을 숨길 수 있습니다.
2. Zero-Day 공격: 방화벽은 이미 알려진 공격 시그니처를 사용하여 트래픽을 검사합니다. 그러나 새로운 공격이나 Zero-Day 공격의 경우, 방화벽은 해당 공격을 감지하지 못할 수 있습니다. 이는 공격자가 이전에 알려지지 않은 취약점을 악용하는 경우입니다.
3. 정상적인 데이터와 혼동: 방화벽은 트래픽의 패턴을 검사하여 악의적인 행위를 감지하려고 시도하지만, 합법적인 데이터와 악의적인 데이터 간의 구별이 어려울 때가 있습니다. 예를 들어, 악성 코드가 데이터 파일의 일부로 숨겨져 있을 수 있습니다.
4. 인간의 사회 엔지니어링: 방화벽은 사람들의 소통을 모니터링하거나 사회 엔지니어링 공격 (사용자를 속이는 공격)을 탐지하기 어렵습니다. 이러한 공격은 주로 사람 간의 상호작용에 의존하므로 방화벽으로 방지하기 어렵습니다.
5. 복잡한 악성코드: 방화벽은 간단한 악성코드를 탐지하는 데 효과적일 수 있지만, 고급 악성코드는 방화벽을 우회하거나 피해갈 수 있습니다.

### 정리

방화벽은 네트워크 보안에 중요한 역할을 하지만, 완벽한 보안을 제공하지는 않습니다.

따라서 다른 보안 솔루션과 함께 사용하여 네트워크와 시스템을 보호하는 것이 일반적입니다.
