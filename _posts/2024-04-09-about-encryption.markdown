---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Encryption
title: About encryption
# title: About encryption
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development, algorithm]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-04-09 09:00:00 +0900
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

## 암호화에 대하여 알아본 글입니다.

안녕하세요!

오늘은 암호 알고리즘과 암호화 기법에 대해 알아보려고 합니다.

글을 본격적으로 시작하기에 앞서,

**---오늘의 TMI---**

얼마전에 생일이라고 실내 아이스 스케이트를 타러 잠실에 갔는데 몸살 걸릴 뻔 했습니다. 아이스링크장에 간다고 옷을 두껍게 입었는데 타다보니 땀이 나서 엄청 덥더라고요. 벗기도 힘든 옷이라 입고 있었더니 하하.. 고수들은 반팔이나 얇은 긴팔을 입고 있었습니다. 제 생각에 가장 이상적인 복장은 반팔에 긴팔 겉옷을 걸치면 조절하기 좋을 것 같습니다! ㅎㅎ

**---TMI 끝---**

글로 돌아가겠습니다!

암호화는 데이터를 안전하게 보호하기 위해 사용되는 기술로, 개인키와 공개키 암호화 기법, 그리고 해시와 솔트에 대해 자세히 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 개인키와 공개키 암호화 기법

개인키와 공개키 암호화 기법은 대칭키 암호화 방식의 한계를 극복하기 위해 개발된 암호화 방식입니다.

개인키 암호화 기법은 하나의 키로 암호화와 복호화를 모두 처리하는 방식이며, 공개키 암호화 기법은 암호화와 복호화를 위한 서로 다른 두 개의 키를 사용하는 방식입니다.

개인키 암호화 기법은 암호화와 복호화에 동일한 키를 사용하기 때문에 빠르지만, 키를 안전하게 관리해야 하는 단점이 있습니다.

공개키 암호화 기법은 공개키로 암호화하고 개인키로 복호화하기 때문에 키를 안전하게 관리할 필요가 없지만, 개인키를 이용한 암호화는 개인키 암호화 기법보다 느릴 수 있습니다.

**대표적인 공개키 암호화 기법**

RSA, DSA, ECC 등이 있으며, 이러한 암호화 기법은 안전한 통신과 데이터 보호에 널리 사용됩니다.

### 해시와 솔트 해시

해시와 솔트 해시는 임의의 길이의 데이터를 고정된 길이의 데이터로 변환하는 알고리즘입니다.

해시 함수는 동일한 입력에 대해서는 항상 동일한 해시 값을 출력하며, 한 번 해시된 데이터는 원래의 데이터로 복원할 수 없습니다.

이러한 특성을 이용하여 암호화보다는 데이터 무결성 검증이나 비밀번호 저장 등에 주로 사용됩니다.

하지만 해시 함수만으로는 보안에 취약할 수 있습니다.

이를 보완하기 위해 솔트(Salt)라는 개념이 도입되었습니다.

솔트는 해시 함수에 추가되는 임의의 값으로, 각각의 데이터에 고유한 해시 값을 생성하기 위해 사용됩니다.

솔트를 사용하면 동일한 데이터에 대해서도 다른 해시 값을 생성하여 보안을 강화할 수 있습니다.

종류와 간단한 소개 암호 알고리즘과 암호화 기법은 다양한 종류가 존재합니다.

몇 가지 대표적인 종류를 간단하게 소개하겠습니다.

- 대칭키 암호화: 암호화와 복호화에 동일한 키를 사용하는 알고리즘으로, DES, AES 등이 있습니다.
- 공개키 암호화: 암호화와 복호화에 서로 다른 키를 사용하는 알고리즘으로, RSA, DSA, ECC 등이 있습니다.
- 해시 함수: 임의의 길이의 데이터를 고정된 길이의 데이터로 변환하는 알고리즘으로, MD5, SHA-1, SHA-256 등이 있습니다.

## 마치며

이상으로 오늘은 암호 알고리즘과 암호화 기법, 그리고 해시와 솔트에 대해 알아보았습니다.

이러한 암호화 기술은 개인정보 보호와 데이터 보안에 중요한 역할을 합니다.

감사합니다.
