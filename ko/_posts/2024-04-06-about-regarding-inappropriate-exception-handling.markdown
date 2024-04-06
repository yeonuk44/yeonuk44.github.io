---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Regarding_Inappropriate_Exception_Handing
title: 부적절한 예외처리에 대하여
# title: Regarding inappropriate exception handling
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
date: 2024-04-06 09:00:00 +0900
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

## 보안의 중요성과 위험에 대하여 알아본 글입니다.

안녕하세요!

글을 본격적으로 시작하기에 앞서,

**---오늘의 TMI---**

오늘 '프랭크 버거'라는 버거 집에서 햄버거와 밀크쉐이크를 먹었는데 너무 맛있었습니다! 개인적으로 1등 버거네요ㅎㅎ 여러분도 기회가 된다면 꼭 한 번 드셔보세요!

**---TMI 끝---**

돌아와서 이번 글에서는 보안에 대한 중요성과 하드코드된 비밀번호의 위험에 대해 이야기해보려고 합니다.

{:data-align="center"}

<!-- outline-end -->

### 개요

많은 웹 애플리케이션과 소프트웨어에서는 비밀번호를 저장하거나 전송할 때 보안을 위해 암호화를 사용합니다.

하지만 여전히 어떤 개발자들은 편의를 위해 비밀번호를 소스 코드에 하드코드하는 경우가 있습니다.

하지만 하드코드된 비밀번호는 매우 큰 보안 위험을 초래할 수 있습니다.

만약 코드가 공개되거나 악의적인 공격자에게 노출된다면, 비밀번호는 쉽게 탈취될 수 있습니다.

이는 사용자들의 개인 정보 유출 및 시스템 침해로 이어질 수 있습니다.

### 하드코드된 비밀번호를 대체할 수 있는 방법

1. 환경 변수를 사용하는 것입니다. 환경 변수는 운영 체제 또는 애플리케이션에서 제공하는 설정 값으로, 암호화된 비밀번호를 저장하는 데 안전한 장소입니다. 이를 통해 소스 코드에 직접 비밀번호를 작성하지 않고도 사용할 수 있습니다.
2. 외부 저장소를 활용하는 것입니다. 암호화된 비밀번호를 외부 저장소에 저장하고, 애플리케이션에서는 해당 저장소에 접근하여 비밀번호를 사용하는 방식입니다. 이렇게 함으로써 비밀번호의 보안성을 높일 수 있습니다.
3. 보안 전문가의 도움을 받는 것도 좋은 방법입니다. 보안 전문가는 최신 보안 기술과 원칙에 대해 잘 알고 있으며, 적절한 보안 솔루션을 제시해줄 수 있습니다. 따라서 보안에 대한 전문적인 조언을 얻는 것은 매우 중요합니다.

보다 안전한 애플리케이션을 개발하고 사용하기 위해서는 하드코드된 비밀번호의 사용을 지양해야 합니다.

대신 암호화된 비밀번호를 안전하게 저장하고, 적절한 보안 방식을 도입하여 사용자들의 개인 정보를 보호해야 합니다.

## 마치며

보안에 대한 중요성을 인식하고, 비밀번호 관리에 대한 적절한 대책을 마련하는 것은 우리 모두의 책임입니다.

앞으로도 보안을 고려한 개발과 사용에 최선을 다해야 합니다. 감사합니다.
