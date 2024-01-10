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

## "캐시 독점"에 대하여

DNS를 학습하며 최근 포스트에서 다룬 웹 캐시에 대한 내용도 일부 포함되어 있습니다.

Cache Poisoning 이하 캐시 독점이라 부르겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 캐시 독점이란?

공격자가 DNS(Domain Name Systm) 서버의 캐시에 잘못된 정보를 삽입하여 유효하지 않은 IP 주소를 반환하도록 조작하는 공격입니다.

유효하지 않은 IP 주소를 반환하게 되면 어떻게 되는가?

공격자는 피해자의 DNS 요청을 조작하고 악의적인 웹사이트로 리디렉션하거나 중간자 공격 등 다양한 공격을 시도할 수 있습니다.

### 중간자 공격이란 무엇인가?

경로 중간에 제삼자가 개입하여 통신 내용을 감청, 조작 또는 위조하는 공격 형태입니다.

이 공격은 통신을 주고받는 양측이 서로 신뢰하는 과정에서 공격자가 사이에 끼어들어 정보를 훔쳐내거나 조작하는 것을 의미합니다.

다시 돌아와 Cache Poisoning은 host head attack 이라고도 불리는데 host head란 무엇일까요?

### host head란?

HTTP 요청에서 사용되는 헤더 중 하나로, 클라이언트가 서버에게 요청하는 도메인 이름을 전달합니다.

이 공격은 호스트 헤더를 조작하여 서버의 응답을 유도하고, 잘못된 응답을 캐시에 저장하도록 만들어 다른 클라이언트들에게도 영향을 미치게 됩니다.

### 결론

캐시 독점은 보안상의 위험이 되므로, DNS 서버 및 웹 서버에서 적절한 방어 및 보호 조치를 취해야 합니다.

이를 위해 캐시 무효화, 캐시 제어 정책, 적절한 DNS 보안 설정 등을 고려해야 합니다.
