---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_K_Means_Clustering
title: K평균 군집화에 대하여
# title: About K-means clustering
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
date: 2024-07-31 09:00:00 +0900
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

## K평균 군집화에 대하여 알아본 글입니다.

안녕하세요!

오늘은 거리측도와 계층적 군집분석에 대하여 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 거리측도 (Distance Measure)

군집분석에서 데이터 간의 유사성을 측정하는 데 사용되는 중요한 요소입니다.

데이터 간의 거리를 계산하여 군집 분석 알고리즘에서 군집 간의 유사성을 판단하는 데 활용됩니다.

대표적인 거리측도로는 유클리드 거리, 맨하탄 거리, 코사인 유사도 등이 있습니다.

#### 유클리드 거리

데이터 포인트 간의 직선 거리를 계산하는 방법으로, 연속형 변수에 적합합니다.

#### 맨하탄 거리

데이터 포인트 간의 수직 및 수평 거리를 계산하는 방법으로, 연속형 변수에 적합합니다.

#### 코사인 유사도

벡터 간의 각도를 이용하여 유사성을 측정하는 방법으로, 텍스트 데이터나 희소한 데이터에 적합합니다.

#### 결론

선택한 거리측도에 따라 군집의 모양과 결과가 달라질 수 있으므로, 데이터의 특성과 목적에 맞는 거리측도를 선택하는 것이 중요합니다.

#### 계층적 군집분석 (Hierarchical Clustering)

계층적 군집분석은 데이터를 순차적 또는 병합적으로 그룹화하여 계층적인 구조로 나타내는 방법입니다.

주어진 데이터들을 거리에 따라 순차적으로 묶어나가거나, 모든 데이터를 하나의 군집으로 시작하여 가장 유사한 데이터들을 순차적으로 묶어가는 방법이 있습니다.

덴드로그램(Dendrogram)은 계층적 군집분석 결과를 시각적으로 나타낸 것으로, 데이터들의 유사성과 군집 간의 구조를 파악하는 데 활용됩니다.

계층적 군집분석은 군집 간의 유사성을 시각적으로 파악할 수 있으며, 데이터 간의 계층적인 구조를 이해하는 데 유용합니다.

### 마치며

이러한 거리측도와 계층적 군집분석은 데이터 간의 유사성을 측정하고, 이를 토대로 군집을 형성하는 데 중요한 방법들로, 데이터의 특성과 목적에 맞게 적절히 선택하는 것이 중요합니다.

감사합니다!
