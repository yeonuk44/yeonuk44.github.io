---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Association_Analysis
title: 연관분석에 대하여
# title: About the association analysis
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
date: 2024-08-03 09:00:00 +0900
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

## 연관분석에 대하여 알아본 글입니다.

안녕하세요!

오늘은 연관분석에 대해 알아보겠습니다.

자기조직화지도 (Self-Organizing Map, SOM)는 비지도 학습 알고리즘으로, 고차원의 데이터를 저차원의 격자 구조에 사상시키는 데 사용됩니다.

아래에서 SOM에 대해 설명하겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 동작 원리

#### 경쟁 학습

입력 데이터와 가장 가까운 뉴런(유닛)을 선택하고, 선택된 뉴런과 그 주변의 뉴런들이 입력 데이터를 통해 경쟁하며 학습합니다.

#### 이웃 관계 조정

학습 초기에는 주변 뉴런들과의 연결이 강하고, 시간이 지날수록 주변 뉴런들과의 연결이 약해지도록 점진적으로 조정됩니다.

#### 맵의 형성

이러한 과정을 통해 입력 데이터의 특성을 보존하면서 저차원의 격자 구조에 사상시키며, 입력 데이터 간의 유사성을 시각적으로 파악할 수 있는 맵을 형성합니다.

### 주요 특징

#### 비선형 사상

SOM은 비선형 사상을 수행하므로, 복잡한 데이터의 구조를 보존하면서 저차원으로 투영할 수 있습니다.

#### 시각화

저차원의 격자 구조에 데이터를 사상시키므로, 데이터 간의 유사성을 시각적으로 파악할 수 있는 맵을 형성합니다.

### 활용

#### 패턴 인식

이미지나 음성과 같은 데이터의 패턴을 인식하는 데 사용됩니다.

#### 클러스터링

데이터의 유사성을 기반으로 군집화하여 시각적으로 표현하는 데 사용됩니다.

### 주의사항

#### 하이퍼파라미터 설정

SOM의 학습률, 이웃 관계 조정 등의 하이퍼파라미터 설정이 결과에 영향을 줄 수 있으므로 주의가 필요합니다.

#### 차원 축소

고차원의 데이터를 저차원으로 사상하는 과정에서 정보의 손실이 발생할 수 있으므로, 이에 대한 고려가 필요합니다.

### 마치며

자기조직화지도는 다양한 분야에서 데이터의 구조를 파악하고 시각적으로 표현하는 데 활용되며, 데이터의 특성을 보존하면서 저차원으로 투영하는 강력한 비지도 학습 알고리즘입니다.

감사합니다!
