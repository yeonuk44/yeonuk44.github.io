---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Normalization_And_Semi_Normalization
title: 정규화와 반정규화에 대하여
# title: About Normalization and Semi-Normalization
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: DB
# multiple tag entries are possible
tags: [db]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-30 09:00:00 +0900
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

## 정규화와 반정규화에 대하여 알아본 글입니다.

안녕하세요!

오늘은 정규화와 반정규화에 대해 알아보곘습니다!

{:data-align="center"}

<!-- outline-end -->

## 정규화(Normalization)

정규화는 데이터베이스 설계 과정에서 중복을 최소화하고 데이터의 일관성을 유지하기 위해 사용되는 프로세스입니다.

주요 목표는 데이터의 중복을 제거하고 삽입, 갱신, 삭제 시 발생할 수 있는 이상 현상을 방지하는 것입니다.

### 목표

1. 데이터 중복 최소화: 하나의 데이터는 한 곳에만 저장되어야 합니다.
2. 데이터 의존성 관리: 데이터베이스의 테이블 간의 종속성을 최소화하여 데이터 수정이나 삭제가 용이해야 합니다.
3. 삽입, 갱신, 삭제 이상 현상 방지: 데이터 삽입, 갱신, 삭제 시 발생할 수 있는 이상 현상(갱신 이상, 삽입 이상, 삭제 이상)을 방지해야 합니다.

### 정규화 과정

1. 제 1 정규화(1NF): 모든 속성 값이 원자적(Atomic)이어야 합니다.
2. 제 2 정규화(2NF): 부분 함수 종속을 제거하여 모든 속성이 후보 키에 대해 완전 함수적 종속이어야 합니다.
3. 제 3 정규화(3NF): 이행적 함수 종속을 제거하여 모든 속성이 후보 키에 대해 이행적 함수 종속이 아니어야 합니다.
4. 보이스-코드 정규화(BCNF): 모든 결정자가 후보 키여야 합니다.

## 반정규화(Denormalization)

반정규화는 데이터베이스의 성능을 향상시키기 위해 정규화된 테이블을 다시 결합하는 프로세스입니다.

주로 읽기 연산이 많은 OLAP(Online Analytical Processing) 환경에서 사용되며, 데이터의 중복을 증가시키고 일부 정규화된 테이블을 다시 합치는 과정입니다.

### 목표

1. 조회 성능 향상: 정규화된 테이블을 다시 합치는 과정으로 인해 조회 연산의 속도를 향상시킵니다.
2. 응답 시간 단축: 대규모 데이터베이스에서 복잡한 쿼리를 실행할 때 응답 시간을 단축시킵니다.
3. 저장 공간 절약: 중복된 데이터의 저장 공간을 절약하고 데이터베이스의 용량을 최적화합니다.

### 반정규화 방법

1. 테이블 합치기: 정규화된 테이블을 다시 결합하여 조회 연산을 최적화합니다.
2. 중복 데이터 추가: 중복 데이터를 추가하여 조회 연산의 속도를 향상시킵니다.
3. 계산된 필드 추가: 복잡한 연산을 필요로 하는 데이터를 미리 계산하여 저장하고 조회 시 사용합니다.

## 마치며

정규화와 반정규화는 데이터베이스 설계에서 데이터의 중복을 최소화하고 데이터베이스의 성능을 향상시키기 위한 두 가지 주요 전략입니다.

정규화는 데이터의 일관성을 유지하고 데이터의 중복을 최소화하는 데 사용되며, 반정규화는 조회 연산의 성능을 향상시키기 위해 데이터를 다시 결합하는 과정입니다.

데이터베이스 설계 시 정규화와 반정규화를 적절히 조합하여 데이터베이스의 성능을 최적화하는 것이 중요합니다.

감사합니다!
