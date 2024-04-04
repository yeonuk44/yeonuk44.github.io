---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Input_Data_Verification_And_Expression
title: 입력 데이터 검증 및 표현에 대하여
# title: About input data verification and expression
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-04-04 09:00:00 +0900
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

## 소프트웨어 개발 보안 구축에 대하여 알아본 글입니다.

안녕하세요! 소프트웨어 개발 보안에 대해 알아보겠습니다.

글을 본격적으로 시작하기에 앞서,

**---오늘의 TMI---**

오늘은 운동을 잘 마치고 육회와 연어 초밥 및 덮밥을 먹었습니다.

너무 맛있더라고요! 역시 운동 후엔 단백질보충! ㅎㅎ

매일 맘 편히 먹기 위해 생존 운동을 하고 있습니다.

운동하고 맛있는거 먹을 생각에 운동도 꾸준히 할 수 있는 것 같습니다.

여러분도 무언가 지속가능한 활동을 하고자 할 때, 인간의 보상심리를 스스로에게 적용해보는 방법은 어떨까요? ㅎㅎ

**---TMI 끝---**

돌아와서 이번 글에서는 Secure SDLC(Secure Software Development Life Cycle) 방법론과 시큐어 코딩의 개념에 대해 알려드리겠습니다.

{:data-align="center"}

<!-- outline-end -->

### Secure SDLC의 개요

Secure SDLC는 소프트웨어 개발 과정에서 보안을 고려한 안전한 소프트웨어를 개발하기 위한 방법론입니다.

전통적인 개발 방법론에 보안 요소를 추가하여 보안 위협으로부터 소프트웨어를 보호하고, 사용자의 개인정보와 기업 자산을 안전하게 보호하는 것이 목표입니다.

### Secure SDLC 방법론 소개

Secure SDLC는 보안을 고려한 다양한 단계로 구성됩니다.

각 단계에서는 보안 요소를 고려하며 보안 활동을 수행합니다.

- 요구사항 분석 단계: 소프트웨어의 보안 요구사항을 분석하고 정의합니다. 사용자 인증, 데이터 암호화 등 보안 관련 요구사항을 확인합니다.
- 설계 단계: 보안 아키텍처를 설계하고 보안 기능을 결정합니다. 시스템의 취약점을 고려하여 보안을 강화하기 위한 설계를 수행합니다.
- 구현 단계: 보안 코딩 가이드라인을 준수하여 보안 취약점을 예방하고, 안전한 코드를 작성합니다. 취약한 함수 사용, 인증 및 권한 검증 등을 확인합니다.
- 테스트 단계: 보안 테스트를 수행하여 취약점을 찾고, 보안 결함을 수정합니다. 페네트레이션 테스트, 코드 리뷰, 취약점 스캐닝 등을 통해 보안을 강화합니다.
- 유지보수 단계: 소프트웨어의 보안 업데이트와 취약점 패치를 수행합니다. 보안 이슈에 대한 대응과 지속적인 강화가 필요합니다.

### 시큐어 코딩의 개념

시큐어 코딩은 취약점을 최소화하고 보안을 강화하기 위해 안전한 코딩 기법을 적용하는 것을 말합니다.

시큐어 코딩은 다음과 같은 개념을 포함합니다.

- 입력 검증: 사용자 입력을 신뢰하지 않고, 유효성을 검증하는 것입니다. 예상치 못한 입력으로 인한 취약점을 방지할 수 있습니다.
- 인증과 권한 검증: 사용자의 신원을 확인하고, 권한을 검증하여 불법적인 접근을 차단합니다.
- 취약한 함수 사용 방지: 취약한 함수 사용은 보안 위협을 초래할 수 있습니다. 안전한 대안 함수나 라이브러리를 사용하여 취약성을 예방합니다.
- 데이터 보호: 데이터의 암호화와 안전한 저장 방법을 고려하여 데이터 노출을 방지합니다.
- 에러 처리: 예외 상황에 대한 적절한 처리를 수행하여 시스템의 취약성을 줄입니다.

## 마치며

이렇게 Secure SDLC와 시큐어 코딩을 통해 소프트웨어 개발 보안을 강화할 수 있습니다.

안전한 소프트웨어를 개발하여 사용자와 기업의 정보를 보호하는 데 주력해야 합니다. 감사합니다.
