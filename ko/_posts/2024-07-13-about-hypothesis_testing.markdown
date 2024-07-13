---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Hypothesis_Testing
title: 가설 검정에 대하여
# title: About hypothesis testing
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
date: 2024-07-13 09:00:00 +0900
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

## 확률 분포의 종류와 추정에 대하여 알아본 글입니다.

안녕하세요!

오늘은 확률 분포의 종류와 추정에 대하여 알아보겠습니다.

확률 분포는 확률 변수가 가질 수 있는 값들과 그 값들이 나타날 확률에 대한 정보를 제공하는 함수입니다.

확률 분포의 종류와 추정에 대해 아래에서 설명하겠습니다.

{:data-align="center"}

<!-- outline-end -->

## 확률 분포의 종류

### 이산형 확률 분포 (Discrete Probability Distribution)

이산형 확률 분포는 이산형 확률 변수가 가질 수 있는 값들과 그 값들이 나타날 확률을 정의합니다.

대표적으로 이항 분포, 포아송 분포 등이 있습니다.

### 연속형 확률 분포 (Continuous Probability Distribution)

연속형 확률 분포는 연속형 확률 변수가 특정 구간에 속할 확률을 정의합니다.

대표적으로 정규 분포, 지수 분포, 균일 분포 등이 있습니다.

## 확률 분포의 추정

확률 분포의 추정은 주어진 데이터를 기반으로 확률 분포의 형태나 모수를 추정하는 과정을 말합니다.

이를 통해 실제 분포를 모르는 상황에서 데이터를 바탕으로 확률 분포를 추정할 수 있습니다.

대표적인 방법으로는 다음과 같은 것들이 있습니다.

### 최대 가능도 추정 (Maximum Likelihood Estimation, MLE)

MLE는 주어진 데이터가 가장 확률이 높은 모수를 찾는 방법으로, 주어진 데이터에 가장 적합한 모수를 찾는데 주로 사용됩니다.

### 최소 제곱 추정 (Least Squares Estimation, LSE)

LSE는 주어진 데이터와 모델 간의 잔차(오차)의 제곱의 합을 최소화하여 모수를 추정하는 방법으로, 회귀 분석에서 많이 사용됩니다.

### 베이지안 추정 (Bayesian Estimation)

베이지안 추정은 사전 분포와 데이터에 기반한 사후 분포를 구하여 모수를 추정하는 방법으로, 불확실성을 확률적으로 다루는 데 사용됩니다.

## 마치며

확률 분포의 종류와 추정은 데이터를 분석하고 모델링하는 데 중요한 요소로, 데이터를 효과적으로 해석하고 모델링하는 데 활용됩니다.

감사합니다!
