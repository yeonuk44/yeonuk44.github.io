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

연관분석에서는 다양한 지표들을 사용하여 상품 간의 연관성을 평가하고 규칙을 도출합니다.

아래에서 연관분석에서 주로 사용되는 지표들에 대해 설명하겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 지지도 (Support)

전체 거래 중에서 특정 항목 집합이 얼마나 자주 발생하는지를 나타내는 지표입니다.

지지도는 다음과 같이 정의됩니다.

지지도 = (특정 항목 집합을 포함하는 거래 수) / (전체 거래 수)

### 신뢰도 (Confidence)

규칙의 신뢰성을 나타내는 지표로, A를 포함하는 거래 중 A와 B가 동시에 포함될 조건부 확률을 의미합니다.

신뢰도는 다음과 같이 정의됩니다.

신뢰도 = (A와 B를 포함하는 거래 수) / (A를 포함하는 거래 수)

### 향상도 (Lift)

두 상품 간의 연관성이 우연에 비해 얼마나 강한지를 나타내는 지표입니다.

향상도는 다음과 같이 정의됩니다.

`향상도 = (지지도) / (A의 지지도 * B의 지지도)`

### 리프트 (Leverage)

두 항목이 독립적일 때의 예상 거래 수와 실제 거래 수의 차이를 나타내는 지표입니다.

리프트는 다음과 같이 정의됩니다.

`리프트 = (A와 B를 포함하는 거래 수) - (A의 지지도 * B의 지지도)`

### 활용

이러한 지표들은 상품 간의 연관성을 측정하고, 유용한 규칙을 발견하는 데 활용됩니다.

예를 들어, 신뢰도가 높은 규칙은 상품 간의 연관성이 강하다고 해석할 수 있고, 향상도가 1보다 큰 경우에는 우연보다 강한 연관성을 나타냅니다.

### 마치며

연관분석에서는 이러한 다양한 지표들을 종합적으로 활용하여 유의미한 규칙을 발견하고, 비즈니스 의사결정에 활용됩니다.

감사합니다!
