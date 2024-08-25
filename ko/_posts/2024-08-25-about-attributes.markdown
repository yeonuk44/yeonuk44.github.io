---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Attributes
title: Attribute에 대하여
# title: About Attributes
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
date: 2024-08-25 09:00:00 +0900
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

## Attribute에 대하여 알아본 글입니다.

안녕하세요!

오늘은 데이터베이스 설계에서 중요한 개념인 **엔터티(Entity)**의 분류에 대해 알아보겠습니다.

엔터티는 데이터베이스의 기본 구성 요소로, 여러 가지 기준에 따라 분류될 수 있습니다.

이번 포스팅에서는 엔터티를 **유형(Entity Type)**과 **발생시점(Entity Occurrence)**에 따라 어떻게 분류할 수 있는지 자세히 살펴보겠습니다.

{:data-align="center"}

<!-- outline-end -->

## 엔터티의 유형 (유형 엔터티 vs 무형 엔터티)

### 유형 엔터티 (Tangible Entity)

#### 정의

유형 엔터티는 물리적으로 존재하는 실체를 나타냅니다.

이러한 엔터티는 실제로 관찰하거나 측정할 수 있는 객체로, 현실 세계에서 물리적 형태를 가지고 있습니다.

#### 예시

- **고객(Customer)**: 고객의 이름, 연락처, 주소 등의 정보를 포함합니다.
- **제품(Product)**: 제품의 이름, 가격, 제조사 등의 정보를 포함합니다.
- **건물(Building)**: 건물의 주소, 크기, 용도 등의 정보를 포함합니다.

#### 특징

- 물리적으로 존재하며, 현실 세계에서 직접 관찰할 수 있습니다.
- 주로 기업의 자산 관리, 재고 관리 등에서 중요한 역할을 합니다.

### 무형 엔터티 (Intangible Entity)

#### 정의

무형 엔터티는 물리적으로 존재하지 않지만 개념적으로 중요한 실체를 나타냅니다.

이러한 엔터티는 물리적 형태는 없지만 데이터베이스에서 중요한 정보로 관리됩니다.

#### 예시

- **계약(Contract)**: 계약 번호, 계약 날짜, 계약 조건 등의 정보를 포함합니다.
- **보험(Insurance)**: 보험 번호, 보험 종류, 보험 금액 등의 정보를 포함합니다.
- **주문(Order)**: 주문 번호, 주문 날짜, 고객 ID, 제품 ID 등의 정보를 포함합니다.

#### 특징

- 물리적 형태는 없지만, 비즈니스 프로세스에서 중요한 역할을 합니다.
- 주로 금융, 법률, 행정 등 다양한 분야에서 사용됩니다.

## 엔터티의 발생시점 (정적 엔터티 vs 동적 엔터티)

### 정적 엔터티 (Static Entity)

#### 정의

정적 엔터티는 시간에 따라 변하지 않거나 변동이 매우 적은 엔터티를 말합니다.

이러한 엔터티는 데이터베이스에 한 번 등록되면 거의 변경되지 않습니다.

#### 예시

- **국가(Country)**: 국가 코드, 국가 이름, 대륙 등의 정보를 포함합니다.
- **통화(Currency)**: 통화 코드, 통화 이름, 환율 등의 정보를 포함합니다.
- **제품 카테고리(Product Category)**: 카테고리 ID, 카테고리 이름 등의 정보를 포함합니다.

#### 특징

- 데이터의 변동이 거의 없으므로 유지보수가 상대적으로 쉽습니다.
- 주로 참조 데이터(Reference Data)로 사용됩니다.

### 동적 엔터티 (Dynamic Entity)

#### 정의

동적 엔터티는 시간에 따라 데이터가 자주 변하는 엔터티를 말합니다.

이러한 엔터티는 비즈니스 활동이나 외부 요인에 의해 지속적으로 변경됩니다.

#### 예시

- **주문(Order)**: 주문 상태, 주문 날짜, 고객 정보 등의 정보가 자주 변경됩니다.
- **고객(Customer)**: 고객의 주소, 연락처, 주문 내역 등의 정보가 자주 변경됩니다.
- **재고(Inventory)**: 재고 수량, 입고 날짜, 출고 날짜 등의 정보가 자주 변경됩니다.

#### 특징

- 데이터가 자주 변경되므로, 데이터베이스 성능과 일관성 유지에 주의가 필요합니다.
- 주로 트랜잭션 데이터(Transaction Data)로 사용됩니다.

## 마치며

엔터티는 데이터베이스 설계의 핵심 요소로, 다양한 기준에 따라 분류될 수 있습니다.

유형에 따라 엔터티를 **유형 엔터티**와 **무형 엔터티**로, 발생시점에 따라 **정적 엔터티**와 **동적 엔터티**로 분류할 수 있습니다.

이러한 분류는 데이터베이스를 설계할 때 엔터티의 특성을 이해하고 적절히 관리하는 데 도움이 됩니다.

데이터베이스 설계 시 엔터티의 유형과 발생시점을 고려하여 더 효율적이고 일관성 있는 데이터 모델을 구축해 보세요.

이를 통해 데이터의 관리와 활용이 더욱 쉬워질 것입니다.

이번 포스팅이 엔터티의 분류에 대해 이해하는 데 도움이 되었기를 바랍니다.
