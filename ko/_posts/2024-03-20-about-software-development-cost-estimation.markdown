---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Software_Development_Cost_Estimation
title: 수학적 산정 기법을 통한 소프트웨어 개발 비용 산정에 대하여
# title: About software development cost estimation using mathematical estimation techniques
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
date: 2024-03-20 09:00:00 +0900
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

## 수학적 산정 기법을 통한 소프트웨어 개발 비용 산정에 대하여 알아본 글입니다.

이 글에서는 Cocomo의 소프트웨어 개발 유형, Putnam 모형, 그리고 기능점수(FP) 모형에 대해 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### Cocomo의 소프트웨어 개발 유형

Cocomo(Model)은 Constructive Cost Model의 약자로, 소프트웨어 개발 비용을 산정하기 위해 사용되는 모델입니다.

Cocomo는 소프트웨어 개발 프로젝트를 세 가지 유형으로 분류합니다.

**Organic**

비교적 작고 단순한 프로젝트에 적합합니다.

개발자들 간의 경험이 풍부하고, 안정된 개발 환경일 때 적용됩니다.

예를 들어, 개인 또는 소규모 팀에 의한 소프트웨어 개발 프로젝트가 여기에 해당합니다.

**Semi-Detached**

조금 더 복잡한 프로젝트에 적합합니다.

일부 팀원들이 경험이 부족하거나, 개발 환경이 상대적으로 안정되지 않을 때 적용됩니다.

예를 들어, 중간 규모의 조직 또는 팀에 의한 소프트웨어 개발 프로젝트가 여기에 해당합니다.

**Embedded**

매우 복잡하고, 신뢰성이 중요한 프로젝트에 적합합니다.

개발 환경이 불확실하거나, 개발자들의 경험이 제한적일 때 적용됩니다.

예를 들어, 임베디드 시스템 또는 고도로 신뢰성이 요구되는 소프트웨어 개발 프로젝트가 여기에 해당합니다.

Cocomo의 소프트웨어 개발 유형은 프로젝트의 특성에 따라 비용 산정 모델을 선택하고, 개발 프로세스를 조정하는 데 도움을 줍니다.

### Putnam 모형

Putnam 모형은 소프트웨어 개발 프로젝트의 크기와 개발에 투입되는 인력 사이의 관계를 나타내는 모델입니다.

이 모델은 소프트웨어 개발에 필요한 인력과 개발 기간 사이의 상관 관계를 분석하여 비용을 산정합니다.

Putnam 모형은 개발 프로젝트의 크기를 기반으로 소프트웨어 개발에 필요한 인력의 양을 추정합니다.

이를 통해 프로젝트의 예상 개발 기간과 비용을 계산할 수 있습니다.

Putnam 모형은 관리자들이 프로젝트 일정을 계획하고 리스크를 관리하는 데 도움을 줍니다.

**기능점수(FP) 모형**

기능점수(FP) 모형은 소프트웨어의 기능적인 측면을 기반으로 비용을 산정하는 모델입니다.

이 모델은 소프트웨어의 기능 요구사항을 기반으로 기능점수를 측정하고, 이를 사용하여 개발 비용을 계산합니다.

FP 모형은 소프트웨어의 기능을 외부 입력, 출력, 데이터 파일, 문서화된 데이터 등의 요소로 분류합니다.

각 요소는 복잡성에 따라 가중치를 부여하여 기능점수를 산정합니다.

이를 통해 개발 비용을 예측하고 프로젝트 일정을 계획할 수 있습니다.

기능점수 모형은 개발자와 고객 간의 의사 소통을 원활하게 하고, 소프트웨어 개발 프로젝트의 비용과 일정을 효과적으로 관리하는 데 도움을 줍니다.

## 마치며

소프트웨어 개발 비용 산정은 프로젝트의 성공과 효율성을 결정하는 중요한 과정입니다.

수학적 산정 기법은 소프트웨어 개발 비용을 정량적으로 산정하기 위해 사용되는 방법론입니다.
