---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Concept_And_Types_Of_Structured_Data_Mining
title: About the concept and types of structured data mining
# title: About the concept and types of structured data mining
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
date: 2024-07-21 09:00:00 +0900
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

## 정형 데이터 마이닝의 개념과 유형에 대하여 알아본 글입니다.

안녕하세요!

오늘은 정형 데이터 마이닝의 개념과 유형에 대하여 알아보겠습니다.

분해시계열 분석은 시계열 데이터를 추세(Trend), 계절성(Seasonality), 주기(Cycle), 랜덤 요인(Error)으로 분해하여 각 구성 요소를 분석하는 방법입니다.

아래에서 분해시계열에 대해 설명하겠습니다.

{:data-align="center"}

<!-- outline-end -->

## 분해시계열 분석의 목적

### 구성 요소의 이해:

시계열 데이터를 구성하는 추세, 계절성, 주기, 랜덤 요인의 특성과 변동성을 이해합니다.

### 예측 모델의 구축

각 구성 요소를 분석하여 예측 모델을 구축하고 미래 값을 예측하는 데 활용합니다.

### 데이터의 특성 파악

데이터의 특성을 파악하여 경향과 주기를 이해하고 추세에 따른 변화를 분석합니다.

## 분해시계열 분석의 종류

### 가법 모형 (Additive Model)

시계열을 추세, 계절성, 주기, 랜덤 요인의 합으로 분해하는 방법으로, Y(t) = T(t) + S(t) + C(t) + E(t)로 나타냅니다.

### 승법 모형 (Multiplicative Model)

시계열을 추세, 계절성, 주기, 랜덤 요인의 곱으로 분해하는 방법으로, Y(t) = T(t) _ S(t) _ C(t) `*` E(t)로 나타냅니다.

## 분해시계열 분석의 단계

### 시계열 데이터의 시각화

시계열 데이터의 추세, 계절성, 주기, 랜덤 요인의 패턴을 파악합니다.

### 추세(Trend) 추정

시계열 데이터에서 장기적인 추세를 추정합니다.

### 계절성(Seasonality) 추정

시계열 데이터에서 계절적인 패턴을 추정합니다.

### 주기(Cycle) 추정

시계열 데이터에서 장기적인 주기적인 요소를 추정합니다.

### 랜덤 요인(Error) 분석

추세, 계절성, 주기를 제외한 나머지 변동을 분석합니다.

## 활용

### 시계열 데이터의 특성 파악

데이터의 추세, 계절성, 주기, 랜덤 요인의 특성을 파악하여 데이터의 구조를 이해합니다.

### 예측 모델의 구축

각 구성 요소를 분석하여 미래 값을 예측하고 예측 모델을 구축하는 데 활용됩니다.

## 마치며

분해시계열 분석은 시계열 데이터의 패턴과 구조를 파악하고 예측하는 데 중요한 기법으로, 다양한 분야에서 활발히 활용되고 있습니다.

감사합니다!
