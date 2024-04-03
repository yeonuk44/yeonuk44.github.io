---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Building_Software_Development_Security
title: About building software development security
# title: About building software development security
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
date: 2024-04-03 09:00:00 +0900
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

## 회복과 병행 제어에 대하여 알아본 글입니다.

안녕하세요!

**---오늘의 TMI---**

오랜만에 아버지께 안부 전화를 드렸습니다. 회사에 있으실 시간인데 갑자기 목소리가 듣고 싶어 전화를 했네요. 사실은.. 전혀 고려하지 못했습니다. 제가 사는 시간과 직장인이 사는 시간대는 다르다는 점을요. 다음부터는 좀 더 세심한 부분까지 고려해야겠습니다. 그럼에도 잘 받아주신 아버지 사랑합니다!

**---TMI 끝---**

돌아와서 이번에는 데이터베이스에서 중요한 개념인 회복과 병행 제어에 대해 알아보겠습니다.

데이터베이스에서 데이터의 일관성을 유지하기 위해 사용되는 이 두 가지 기법은 중요하고 필수적인 개념입니다.

지금부터 자세히 살펴보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 회복 (Recovery)

회복은 데이터베이스에서 시스템 장애 또는 오류로부터 복구하는 과정을 의미합니다.

시스템 장애가 발생하면 데이터의 일관성과 무결성이 손상될 수 있습니다.
회복 기법은 이러한 손상된 데이터를 원래의 일관된 상태로 복구하는 과정을 말합니다.

### 즉각 갱신 기법 (Immediate Update Technique)

즉각 갱신 기법은 데이터베이스에서 데이터를 갱신할 때, 해당 갱신 작업을 즉시 디스크에 반영하는 방식을 말합니다.

이렇게 함으로써 데이터의 일관성을 유지하고, 시스템 장애가 발생했을 때 복구 작업을 최소화할 수 있습니다.

### 병행 제어 (Concurrency Control)

병행 제어는 동시에 여러 사용자가 데이터베이스를 접근하고 갱신하는 상황에서 데이터 일관성을 보장하기 위한 기법입니다.

병행 처리 시 여러 트랜잭션이 동시에 실행되면서 갱신 작업이 겹칠 수 있습니다.

이러한 상황에서 병행 제어 기법은 데이터 일관성을 유지하기 위해 트랜잭션들의 실행을 제어하고 조정합니다.

### 로킹 (Locking)

로킹은 병행 제어에서 사용되는 주요한 기법 중 하나입니다.

로킹은 트랜잭션이 데이터를 접근할 때 해당 데이터에 대한 잠금을 설정하는 것을 의미합니다.

한 트랜잭션이 데이터를 갱신하는 동안 다른 트랜잭션이 해당 데이터를 접근하지 못하도록 합니다.

이를 통해 데이터의 일관성을 유지하고 갱신 충돌을 방지할 수 있습니다.

### 타임 스탬프 순서 (Timestamp Ordering)

타임 스탬프 순서는 트랜잭션들의 실행 순서를 결정하기 위해 사용되는 기법입니다.

각 트랜잭션에는 고유한 타임 스탬프가 부여되고, 이를 기반으로 트랜잭션들의 실행 순서를 결정합니다.

이를 통해 갱신 작업의 충돌을 방지하고 데이터 일관성을 유지할 수 있습니다.

### 로킹 단위 (Locking Granularity)

로킹 단위는 로킹을 적용하는 단위를 의미합니다.

로킹 단위는 데이터베이스의 크기와 트랜잭션의 성격에 따라 결정됩니다.

예를 들어, 로우 레벨 로킹은 개별 데이터 레코드에 대한 로킹을 의미하고, 테이블 레벨 로킹은 전체 테이블에 대한 로킹을 의미합니다.

## 마치며

회복과 병행 제어는 데이터베이스 시스템에서 데이터의 일관성과 무결성을 유지하기 위해 중요한 요소입니다.

이를 효과적으로 구현하면 데이터베이스 시스템의 안정성과 신뢰성을 높일 수 있습니다.

따라서 개발자들은 회복과 병행 제어에 대한 이해와 적절한 적용을 통해 데이터베이스 시스템을 보다 안정적으로 운영할 수 있습니다.
