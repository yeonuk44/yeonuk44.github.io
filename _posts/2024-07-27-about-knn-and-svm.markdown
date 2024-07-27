---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_KNN_And_SVM
title: About KNN and SVM
# title: About KNN and SVM
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
date: 2024-07-27 09:00:00 +0900
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

## KNN과 SVM에 대하여 알아본 글입니다.

안녕하세요!

오늘은 KNN과 SVM에 대하여 알아보겠습니다.

인공신경망(Artificial Neural Network, ANN)은 사람의 뇌의 뉴런 체계에서 영감을 받은 기계 학습 모델로, 복잡한 비선형 관계를 학습하고 예측하는데 사용됩니다.

{:data-align="center"}

<!-- outline-end -->

## 주요 개념

### 뉴런(Neuron)

인공신경망은 인공적으로 구현된 뉴런으로 이루어진 모델로, 입력을 받아 가중치를 곱하고 활성화 함수를 통해 출력을 생성합니다.

### 은닉층(Hidden Layer)

입력층과 출력층 사이에 위치한 층으로, 입력 데이터의 비선형 관계를 학습하는 데 사용됩니다.

### 가중치(Weight)

입력과 은닉층, 은닉층과 출력층 사이의 연결에 대해 부여된 중요도를 나타내는 매개변수입니다.

## 동작 원리

### 순전파(Forward Propagation)

입력 데이터가 신경망을 통과하여 출력층으로 전파되는 과정으로, 각 층의 가중치와 활성화 함수를 통해 출력이 계산됩니다.

### 역전파(Backward Propagation)

출력과 실제 값 사이의 오차를 계산하고, 이 오차를 각 층의 가중치에 역방향으로 전파하여 가중치를 조정하는 과정입니다.

## 주요 알고리즘

### 다층 퍼셉트론(Multilayer Perceptron, MLP)

여러 개의 은닉층을 가진 신경망으로, 복잡한 비선형 문제를 해결하는 데 사용됩니다.

### 합성곱 신경망(Convolutional Neural Network, CNN)

이미지 분류, 객체 검출, 영상 처리 등에 특화된 신경망으로, 합성곱과 풀링을 통해 지역적인 정보를 학습하는 데 사용됩니다.

### 순환 신경망(Recurrent Neural Network, RNN)

순서가 있는 데이터(시계열 데이터, 자연어 등)를 모델링하는 데 사용되며, 기억 구조를 통해 순서 정보를 유지하는 데 효과적입니다.

## 활용

### 이미지 인식

CNN을 통해 얼굴 인식, 물체 감지 등의 작업을 수행합니다.

### 자연어 처리

RNN을 활용하여 기계 번역, 문장 생성, 감성 분석 등에 사용됩니다.

### 금융 예측

주가 예측, 시계열 데이터 분석 등에 활용됩니다.

## 주의사항

### 과적합

큰 규모의 신경망에서는 과적합 문제에 주의해야 합니다.

### 하이퍼파라미터 조정

신경망의 성능은 다양한 하이퍼파라미터에 의해 크게 영향을 받으므로, 적절한 조정이 필요합니다.

## 마치며

인공신경망은 다양한 분야에서 활용되며, 복잡하고 비선형적인 문제를 해결하는 데 효과적으로 사용됩니다.

감사합니다!
