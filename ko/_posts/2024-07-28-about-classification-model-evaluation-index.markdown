---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Classification_Model_Evaluation_Index
title: 분류모델 평가지표에 대하여
# title: About the classification model evaluation index
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
date: 2024-07-28 09:00:00 +0900
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

## 분류모델 평가지표에 대하여 알아본 글입니다.

안녕하세요!

오늘은 분류모델 평가지표에 대하여 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### K-최근접 이웃 (K-Nearest Neighbors, KNN)

K-최근접 이웃(KNN)은 분류 및 회귀 문제에 사용되는 지도 학습 알고리즘 중 하나입니다. 아래에서 KNN에 대해 설명하겠습니다.

#### 동작 원리

- 이웃의 선택: 새로운 데이터 포인트와 가장 가까운 K개의 이웃을 선택합니다.
- 다수결 투표: 분류 문제의 경우 K개의 이웃 중 다수결 투표를 통해 새로운 데이터 포인트의 클래스를 결정합니다. 회귀 문제의 경우 K개의 이웃의 평균을 예측값으로 사용합니다.

#### 장단점

- 장점: 구현이 간단하며, 훈련 단계가 빠르고 직관적입니다.
- 단점: 예측 단계에서 모든 훈련 데이터와의 거리를 계산해야 하므로 계산 비용이 높을 수 있습니다.

#### 활용

- 이상치 탐지: 이상치 탐지에 사용될 수 있습니다.
- 추천 시스템: 비슷한 사용자 또는 상품을 찾는 데 사용될 수 있습니다.

### 서포트 벡터 머신 (Support Vector Machine, SVM)

서포트 벡터 머신(SVM)은 분류 및 회귀 문제에 사용되는 지도 학습 알고리즘으로, 데이터를 고차원 공간으로 매핑하여 최적의 결정 경계를 찾는 데 사용됩니다.

#### 동작 원리

- 초평면(Decision Boundary) 찾기: 데이터를 분리하는 최적의 초평면을 찾습니다.
- 서포트 벡터(Support Vector) 찾기: 초평면에 가장 가까이 있는 데이터 포인트인 서포트 벡터를 찾습니다.
- 커널 기법(Kernel Trick): 비선형 문제를 해결하기 위해 커널 함수를 사용하여 데이터를 고차원 공간으로 매핑합니다.

#### 장단점

- 장점: 고차원 데이터에서 우수한 성능을 보이며, 커널 기법을 통해 비선형 문제를 해결할 수 있습니다.
- 단점: 모델의 해석이 어려우며, 데이터 전처리와 매개변수 설정에 민감합니다.

#### 활용

- 이진 및 다중 클래스 분류: 분류 문제에 폭넓게 사용됩니다.
- 이상치 탐지: 이상치 탐지에 사용될 수 있습니다.

### 마치며

KNN과 SVM은 각각의 특징에 따라 다양한 문제에 유용하게 활용되는 지도 학습 알고리즘입니다.

감사합니다!
