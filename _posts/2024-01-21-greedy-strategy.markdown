---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Greedy_Strategy
title: About the Greedy Strategy
# title: About the Greedy Strategy (Greedy Algorithm)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Algorithm
# multiple tag entries are possible
tags: [algorithm]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-21 09:00:00 +0900
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

## "트랜스페어런트 프록시(Transparent Proxy)"에 대하여

이전에 "네트워크 보안에서 중요한 역할을 하는 포워드 프록시와 리버스 프록시"라는 제목으로 글을 작성한 바가 있습니다.

해당 글에선 이전 주제에 이은 프록시에 관련한 주제로 학습했던 것을 기록으로 남기고자 합니다.

{:data-align="center"}

<!-- outline-end -->

### 소개

인터넷에서 데이터를 주고받을 때, 정보는 다양한 경로를 통해 이동합니다.

이런 경로 중 하나에는 "프록시(Proxy)"가 있습니다.

프록시는 클라이언트와 서버 간의 통신을 중계하고 보안, 성능 최적화, 캐싱 등 다양한 목적으로 사용됩니다.

그 중에서도 "트랜스페어런트 프록시"는 특별한 유형의 프록시 서버로, 그 이름처럼 투명하게 동작하는데, 이 글에서는 이러한 트랜스페어런트 프록시에 대해 자세히 알아보겠습니다.

#### 트랜스페어런트 프록시란?

트랜스페어런트 프록시는 클라이언트와 서버 간의 통신을 중계하는 중간 매개체로, 클라이언트와 서버가 서로에게 서로를 프록시 서버로 사용한다는 특징을 갖습니다.

이것은 사용자나 애플리케이션에게 프록시 서버의 존재를 숨기고 네트워크 트래픽을 투명하게 중계한다는 뜻입니다.

트랜스페어런트 프록시는 사용자나 애플리케이션에게는 눈에 띄지 않으며, 네트워크 트래픽을 중개하면서 그 내용을 변경하지 않습니다.

#### 동작 원리

트랜스페어런트 프록시의 주요 특징 중 하나는 "투명성"입니다.

이것은 사용자나 애플리케이션이 프록시 서버의 존재를 모르는 것을 의미합니다.

프록시 서버는 네트워크 장비나 애플리케이션 설정에서 사용자의 인식 없이 중간에서 동작합니다.

트랜스페어런트 프록시는 클라이언트가 서버에 접근할 때 중간에 위치하여 클라이언트의 요청을 받고 서버에 전달합니다.

서버로부터의 응답 역시 중간에서 받아 클라이언트에 전달합니다.

이 과정에서 프록시는 클라이언트와 서버 사이의 중계 역할을 수행하며, 트래픽을 모니터링하거나 필요한 경우 캐싱, 보안 검사, 로깅 등을 수행할 수 있습니다.

#### 트랜스페어런트 프록시의 활용

트랜스페어런트 프록시는 다양한 용도로 활용됩니다.

그 중 일부를 살펴보겠습니다.

- 캐싱: 트랜스페어런트 프록시는 서버에서 받은 응답을 캐싱하여 이후 동일한 요청에 빠르게 응답할 수 있습니다. 이는 성능 최적화에 도움이 됩니다.
- 보안 검사: 프록시는 네트워크 트래픽을 검사하여 악성 코드나 해킹 시도를 탐지하고 차단할 수 있습니다.
- 로깅 및 감시: 프록시는 네트워크 활동을 모니터링하고 로그를 기록하여 보안 및 오류 진단을 위해 사용될 수 있습니다.

#### 결론

트랜스페어런트 프록시는 네트워크 통신을 중계하면서 사용자나 애플리케이션에게는 투명하게 동작합니다.

그 동안 네트워크 트래픽을 모니터링하고 보안, 성능 최적화, 캐싱 등 다양한 목적으로 활용됩니다.

이러한 투명한 중계 서버는 네트워크 관리와 보안에 핵심적인 역할을 합니다.
