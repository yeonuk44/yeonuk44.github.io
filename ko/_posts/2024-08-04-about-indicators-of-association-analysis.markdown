---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Indicators_Of_Association_Analysis
title: 연관분석의 지표에 대하여
# title: About the indicators of association analysis
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Statistics
# multiple tag entries are possible
tags: [statistics]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-04 09:00:00 +0900
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

## 연관분석의 지표에 대하여 알아본 글입니다.

안녕하세요!

오늘은 연관분석의 지표에 대하여 알아보겠습니다.

연관분석은 대규모 데이터 세트에서 항목들 간의 흥미로운 관계를 발견하는 데이터 마이닝 기법 중 하나입니다.

이를 통해 상품의 연관성을 파악하거나 규칙을 도출하여 비즈니스적인 의사결정에 활용됩니다.

아래에서 연관분석에 대해 설명하겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 주요 개념

#### 지지도 (Support)

규칙의 전체 출현 빈도를 나타내며, 특정 항목 집합이 전체 거래 중 얼마나 많이 발생했는지를 나타냅니다.

#### 신뢰도 (Confidence)

A를 포함하는 거래 중 A와 B가 동시에 포함될 확률을 나타내며, 지지도가 높은 규칙들 중에서 A와 B의 관계가 얼마나 강한지를 나타냅니다.

#### 향상도 (Lift)

A와 B의 관계가 우연에 비해 얼마나 자주 발생하는지를 나타내며, 1보다 크면 두 항목 간의 양의 상관관계가 있음을 나타냅니다.

### 활용

#### 상품 권장 시스템

상품 간의 연관성을 파악하여 고객에게 권장 상품을 제시하는 데 사용됩니다.

#### 재고 관리

상품의 연관성을 파악하여 한 상품의 판매가 증가할 때 다른 상품의 재고를 미리 조정하는 데 사용됩니다.

### 알고리즘

#### Apriori 알고리즘

빈발 항목 집합을 탐색하여 연관 규칙을 생성하는 데 사용되며, 지지도와 신뢰도를 기반으로 규칙을 생성합니다.

#### FP-Growth 알고리즘

빈발 패턴을 찾기 위해 FP-트리(Frequent Pattern Tree)를 구축하고, 이를 이용하여 빈발 항목 집합을 추출하는 데 사용됩니다.

### 주의사항

#### 데이터 전처리

데이터의 품질을 향상시키기 위해 노이즈나 이상치를 제거하는 등의 전처리가 필요합니다.

#### 패턴 해석

발견된 연관 규칙을 비즈니스에 적용하기 전에 그 의미와 타당성을 신중하게 검토해야 합니다.

### 마치며

연관분석은 다양한 분야에서 상품 추천, 마케팅 전략 수립, 재고 관리 등에 활용되며, 효율적인 규칙을 발견하여 비즈니스에 유용한 통찰을 제공하는 강력한 데이터 마이닝 기법입니다.

감사합니다!
