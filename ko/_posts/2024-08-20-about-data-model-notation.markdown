---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Data_Model_Notation
title: 데이터 모델 표기법에 대하여
# title: About data model notation
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Data
# multiple tag entries are possible
tags: [data]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-20 09:00:00 +0900
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

## 데이터 모델 표기법에 대하여 알아본 글입니다.

안녕하세요!

데이터 모델링은 데이터를 체계적으로 구조화하고, 데이터베이스 시스템을 설계하는 중요한 과정입니다.

이 과정에서 성공적인 데이터 모델링을 위해 반드시 고려해야 하는 세 가지 핵심 요소가 있습니다.

엔티티, 속성, 관계입니다.

이번 포스팅에서는 데이터 모델링의 기초가 되는 이 세 가지 요소에 대해 자세히 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

## 엔티티 (Entity)

### 엔티티란?

엔티티는 데이터베이스에서 관리해야 할 데이터 객체를 의미합니다.

이는 현실 세계에서 존재하는 독립적인 개체로, 데이터베이스에서 정보를 저장할 수 있는 대상이 됩니다.

예를 들어, 고객, 제품, 주문 등이 엔티티에 해당합니다.

### 엔티티의 특징

- 독립성: 엔티티는 고유한 식별자를 통해 독립적으로 존재합니다.
- 구체성: 엔티티는 구체적인 개체를 나타내며, 실제 데이터를 담고 있습니다.
- 속성 집합: 각 엔티티는 여러 개의 속성을 가지고 있어, 이를 통해 엔티티의 특성을 정의합니다.

### 엔티티 예시

- 고객: 고객 ID, 이름, 연락처, 주소
- 제품: 제품 ID, 이름, 가격, 제조사
- 주문: 주문 ID, 주문 날짜, 고객 ID, 제품 ID

## 속성 (Attribute)

### 속성이란?

속성은 엔티티의 특성을 나타내는 정보의 단위를 말합니다.

각 엔티티는 여러 개의 속성으로 구성되며, 이러한 속성들이 모여 엔티티의 구체적인 정보를 형성합니다.

예를 들어, 고객 엔티티의 속성으로는 이름, 연락처, 주소 등이 있습니다.

### 속성의 유형

- 기본 속성 (Simple Attribute): 더 이상 나눌 수 없는 단일 속성입니다. 예: 이름, 생년월일
- 복합 속성 (Composite Attribute): 여러 개의 하위 속성으로 구성된 속성입니다. 예: 주소 (도시, 도로명, 우편번호 등)
- 파생 속성 (Derived Attribute): 다른 속성을 이용하여 계산된 속성입니다. 예: 총 주문 금액 (단가 × 수량)

### 속성 예시

- 고객 엔티티: 고객 ID, 이름, 연락처, 주소
- 제품 엔티티: 제품 ID, 이름, 가격, 제조사
- 주문 엔티티: 주문 ID, 주문 날짜, 고객 ID, 제품 ID

## 관계 (Relationship)

### 관계란?

관계는 엔티티 간의 상호작용이나 연관성을 나타냅니다.

데이터 모델링에서는 엔티티 간의 관계를 정의하여 데이터 구조를 보다 명확하고 체계적으로 만듭니다.

관계는 두 개 이상의 엔티티 사이에서 발생할 수 있습니다.

### 관계의 종류

- 일대일 (One-to-One): 한 엔티티가 다른 엔티티와 단 하나의 연관을 가지는 경우입니다. 예: 직원과 사원증
- 일대다 (One-to-Many): 한 엔티티가 여러 엔티티와 연관을 가지는 경우입니다. 예: 고객과 주문
- 다대다 (Many-to-Many): 여러 엔티티가 여러 엔티티와 연관을 가지는 경우입니다. 예: 학생과 강의

### 관계 예시

- 고객과 주문: 한 고객이 여러 주문을 할 수 있음 (일대다 관계)
- 제품과 주문: 한 주문에 여러 제품이 포함될 수 있음 (다대다 관계)
- 직원과 사원증: 각 직원은 하나의 사원증을 가짐 (일대일 관계)

## 마치며

데이터 모델링에서 엔티티, 속성, 관계는 기본적이면서도 매우 중요한 요소입니다.

엔티티는 데이터베이스에서 관리할 주요 객체를 정의하고, 속성은 각 엔티티의 구체적인 특성을 나타내며, 관계는 엔티티 간의 상호작용을 명확히 합니다.

이 세 가지 요소를 잘 이해하고 활용하면, 효율적이고 체계적인 데이터 구조를 설계할 수 있습니다.

데이터 모델링을 통해 데이터베이스 시스템을 설계할 때, 이 세 가지 요소를 항상 염두에 두고, 명확하고 일관된 데이터 구조를 구축해 보세요.

이를 통해 더 나은 데이터 관리와 분석이 가능해지며, 궁극적으로 비즈니스의 성공에 기여할 수 있을 것입니다.
