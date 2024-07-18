---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Correlation_Analysis_In_Multivariate_Analysis
title: 다변량 분석에서 상관분석에 대하여
# title: About correlation analysis in multivariate analysis
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
date: 2024-07-18 09:00:00 +0900
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

## 다차원 척도법과 주성분 분석에 대하여 알아본 글입니다.

안녕하세요!

오늘은 다차원 척도법과 주성분 분석에 대하여 알아보겠습니다.

다차원 척도법(Multidimensional Scaling, MDS)과 주성분 분석(Principal Component Analysis, PCA)은 데이터의 차원을 축소하고 시각화하는 데 사용되는 통계적 기법입니다.

아래에서 각각에 대해 설명하겠습니다.

{:data-align="center"}

<!-- outline-end -->

## 다차원 척도법 (MDS)

### 개념

MDS는 고차원 공간에 있는 데이터의 상대적 거리 및 유사성을 보존하면서 저차원으로 사상하는 기법입니다.

데이터 간의 유사성을 시각적으로 표현하는 데 사용됩니다.

### 활용

MDS는 주로 다차원적인 데이터를 시각적으로 표현하거나 유사성을 분석하는 데 사용됩니다.

예를 들어, 소비자들이 제품들을 어떻게 인식하는지, 지리적 위치들 간의 상대적 거리 등을 분석하는 데 활용됩니다.

### 종류

MDS에는 거리 행렬을 이용하는 비메트릭 MDS와 내적을 이용하는 메트릭 MDS 등이 있습니다.

## 주성분 분석 (PCA)

### 개념

PCA는 다변량 자료의 차원을 축소하고 주요한 정보를 추출하는 기법으로, 변수들 간의 상관관계를 이용하여 기존 변수들을 선형적으로 결합한 새로운 변수들을 찾아냅니다.

### 활용

PCA는 다변량 자료의 차원 축소, 잠재적인 요인의 발견, 데이터 압축, 잡음 제거 등 다양한 분야에서 활용됩니다.

### 주요 개념

PCA는 데이터의 분산을 최대화하는 새로운 변수(주성분)를 찾아내며, 원래 변수들의 정보를 최대한 보존하는데 중점을 둡니다.

## 공통점과 차이점

### 공통점

MDS와 PCA 모두 다차원 데이터를 저차원으로 축소하여 시각화하거나 데이터의 주요한 구조를 추출하는 데 사용됩니다.

### 차이점

MDS는 데이터 간의 거리나 유사성을 보존하는 데 중점을 두고, PCA는 변수들 간의 상관관계를 최대화하는 데 중점을 둡니다.

## 마치며

다차원 척도법과 주성분 분석은 다변량 데이터의 시각화와 구조를 이해하는 데 중요한 도구로 활용됩니다.

감사합니다!
