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

## 가설 검정에 대하여 알아본 글입니다.

안녕하세요!

오늘은 가설 검정에 대하여 알아보겠습니다.

가설 검정은 통계적으로 어떤 가설이 옳은지 여부를 결정하는 과정을 말합니다.

일반적으로 가설 검정은 귀무 가설과 대립 가설을 설정하고, 주어진 데이터를 바탕으로 귀무 가설을 기각하거나 채택하는 과정으로 진행됩니다.

아래는 가설 검정과 함께 문제풀이 예시에 대한 내용입니다.

{:data-align="center"}

<!-- outline-end -->

## 가설 검정의 단계

### 가설 설정

귀무 가설(H0)과 대립 가설(H1)을 설정합니다.

귀무 가설은 일반적인 주장을, 대립 가설은 새로운 주장을 나타냅니다.

### 유의수준 설정

가설을 검정할 때 얼마나 강력한 증거가 필요한지를 결정하는 수준을 설정합니다.

일반적으로 0.05 또는 0.01 수준이 많이 사용됩니다.

### 통계량 계산

주어진 데이터를 바탕으로 적절한 통계량(예: t-검정, Z-검정, 카이제곱 검정 등)을 계산합니다.

### P-값 계산

계산된 통계량에 대한 확률 값을 계산하여, 귀무 가설이 참일 때 주어진 데이터에서 관측된 결과나 더 극단적인 결과를 얻을 확률을 의미합니다.

### 결정

P-값을 유의수준과 비교하여 귀무 가설을 기각하거나 채택합니다.

유의수준보다 작은 P-값을 가진다면 귀무 가설을 기각하고, 그렇지 않다면 귀무 가설을 채택합니다.

### 문제풀이 예시

가설 검정의 문제풀이 예시로는 "어떤 약이 복용 전과 후의 효과에 차이가 있는가?"와 같은 문제가 있을 수 있습니다.

이 경우에는 복용 전과 후의 결과를 측정하여 통계적으로 유의한 차이가 있는지를 검정합니다.

가령, 복용 전과 후의 평균 효과를 비교하여 두 그룹 간의 차이가 우연에 의한 것인지를 확인하는 것이 가설 검정의 한 예시입니다.

이를 통해 약의 효과에 대한 통계적인 근거를 얻을 수 있습니다.

## 마치며

가설 검정은 데이터 분석에서 중요한 단계로, 통계적으로 결과를 검증하고 결론을 도출하는 데 활용됩니다.
