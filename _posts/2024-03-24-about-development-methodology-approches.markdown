---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Software_Development_Methodology_Approaches
title: About software development methodology approaches
# title: About software development methodology approaches
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: PM
# multiple tag entries are possible
tags: [pm]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-03-24 09:00:00 +0900
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

## 상향식 비용 산정 기법에 대하여 알아본 글입니다.

상향식 비용 산정 기법은 소프트웨어 개발 비용을 추정하기 위해 사용되는 방법 중 하나입니다.

이 기법은 소프트웨어 개발 프로젝트의 규모와 복잡성을 고려하여 개발에 필요한 리소스와 시간을 산정하는 데에 초점을 맞춥니다.

이번 글에서는 상향식 비용 산정 기법의 개요, LOC(Line of Code) 기법, 그리고 개발 단계별 인월수 기법에 대해 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 상향식 비용 산정 기법 개요

상향식 비용 산정 기법은 소프트웨어 개발 비용을 프로젝트의 규모와 관련된 요소를 기반으로 예측하는 방법입니다.

이 기법은 프로젝트의 크기, 복잡성, 개발 환경 등을 고려하여 소프트웨어 개발에 필요한 리소스를 추정합니다.

상향식 비용 산정 기법은 초기에는 보다 추상적인 수준에서 비용을 산정하고, 개발 과정이 진행됨에 따라 세부적인 비용 산정을 수행합니다.

### LOC(Line of Code) 기법

LOC 기법은 소프트웨어 개발에 참여하는 코드의 행(Line) 수를 기반으로 비용을 산정하는 방법입니다.

이 기법은 개발자가 작성한 소스 코드의 양을 통해 프로젝트의 규모를 추정하고, 이를 바탕으로 개발에 필요한 시간과 리소스를 계산합니다.

일반적으로 LOC 기법은 과거의 프로젝트 데이터나 표준화된 행(Line) 수에 따른 산정 모델을 사용하여 비용을 예측합니다.

### 개발 단계별 인월수 기법

개발 단계별 인월수 기법은 개발 과정을 여러 단계로 나누고, 각 단계에서 필요한 인력의 인월수(Man-Month)를 산정하는 방법입니다.

이 기법은 소프트웨어 개발 프로세스를 요구사항 분석, 설계, 코딩, 테스트 등의 단계로 세분화하고, 각 단계에 필요한 인력의 인월수를 추정합니다.

이때 인월수는 개발자 한 명이 한 달 동안 일할 수 있는 시간으로 계산됩니다.

## 마치며

상향식 비용 산정 기법은 소프트웨어 개발 비용을 예측하기 위해 유용한 방법입니다.

LOC 기법은 개발자가 작성한 코드의 양을 기반으로 비용을 산정하며, 개발 단계별 인월수 기법은 개발 과정을 단계별로 세분화하여 인력의 인월수를 산정합니다.

이러한 비용 산정 기법들은 개발 프로젝트의 효율성과 예산 관리에 중요한 역할을 합니다.

그러나 비용 산정은 항상 정확한 예측을 보장하지는 않으므로, 다양한 요소를 고려하고 유연성을 가지는 것이 중요합니다.
