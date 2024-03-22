---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Developmental_Trends_In_Engineering
title: About the developmental trends in S/W engineering
# title: About the developmental trends in S/W engineering
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
date: 2024-03-22 09:00:00 +0900
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

## 프로젝트 일정 계획과 관리 방법에 대하여 알아본 글입니다.

효과적인 프로젝트 일정 계획을 위해 PERT(Program Evaluation and Review Technique), CPM(Critical Path Method), 그리고 간트 차트(Gantt Chart)와 같은 도구와 기법이 사용됩니다.

이 글에서는 각각의 개념과 그 특징을 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### PERT (Program Evaluation and Review Technique)

PERT는 프로젝트 일정 계획과 관리에 사용되는 확률적인 방법론입니다.

주로 복잡하고 비선형적인 프로젝트에 적용됩니다.

PERT는 다음과 같은 요소들을 사용하여 프로젝트 일정을 계획하고 관리합니다.

- 이벤트(Event): 프로젝트에서 발생하는 특정한 사건 또는 결과물을 나타냅니다. 예를 들어, "시스템 설계 완료" 또는 "코딩 완료"와 같은 이벤트가 있을 수 있습니다.
- 활동(Activity): 프로젝트에서 수행되는 작업 단위를 나타냅니다. 각 활동은 시작 및 종료 이벤트와 연결되어 있습니다.
- 시간 추정(Time Estimation): 각 활동에 대한 소요 시간을 추정합니다. PERT에서는 세 가지 시간 추정치를 사용합니다: 최적 시간(예상 소요 시간의 하한값), 기대 시간(예상 소요 시간의 평균값), 최악 시간(예상 소요 시간의 상한값).

PERT는 이러한 요소들을 기반으로 프로젝트 일정에 대한 확률적인 예측을 제공합니다.

이를 통해 프로젝트 관리자는 리스크를 식별하고 우선순위를 정할 수 있습니다.

### CPM (Critical Path Method)

CPM은 프로젝트 일정 계획과 관리에 사용되는 간단하면서도 강력한 방법론입니다.

CPM은 프로젝트에서 가장 긴 경로인 "임계 경로(Critical Path)"를 특정하여 프로젝트의 최소 기간을 결정합니다.

CPM은 다음과 같은 단계로 프로젝트 일정을 계획하고 관리합니다.

- 활동 식별(Activity Identification): 프로젝트에서 수행되는 모든 활동을 식별하고 기록합니다.
- 선후행 관계 정의(Precedence Relationship Definition): 각 활동 간의 선후관계를 정의합니다. 이를 통해 프로젝트의 논리적인 흐름을 설정합니다.
- 시간 추정(Time Estimation): 각 활동에 대한 소요 시간을 추정합니다. CPM에서는 일반적으로 한 가지 시간 추정치를 사용합니다.
- 네트워크 다이어그램(Network Diagram) 작성: 활동과 선후행 관계를 기반으로 네트워크 다이어그램을 작성합니다.
- 임계 경로 결정(Critical Path Determination): 네트워크 다이어그램을 통해 프로젝트의 임계 경로를 식별합니다. 임계 경로는 프로젝트의 최소 기간을 결정하는 핵심 경로입니다.

CPM은 임계 경로를 중심으로 프로젝트 일정을 계획하고, 이를 통해 프로젝트의 진행 상황을 모니터링할 수 있습니다.

### 간트 차트 (Gantt Chart)

간트 차트는 프로젝트 일정을 시각적으로 표현하는 도구입니다.

일정 계획에 포함된 활동들과 해당 활동의 시작 및 종료 날짜를 막대 그래프로 나타냅니다.

간트 차트는 다음과 같은 요소들을 포함합니다.

- 활동(Activity): 프로젝트에서 수행되는 작업 단위를 나타냅니다. 각 활동은 막대 그래프로 표현됩니다.
- 시간(Time): 각 활동의 시작 및 종료 날짜를 표시합니다. 이를 통해 프로젝트 일정을 시각적으로 파악할 수 있습니다.
- 마일스톤(Milestone): 프로젝트의 중요한 이벤트 또는 목표를 나타냅니다. 간트 차트에 표시되는 특별한 기호로 표시됩니다.

간트 차트는 프로젝트 일정을 쉽게 이해하고 관리할 수 있는 도구입니다.

시각적인 표현을 통해 프로젝트의 진행 상황과 작업간의 관계를 파악할 수 있습니다.

## 마치며

프로젝트 일정 계획은 프로젝트의 성공과 효율성을 결정하는 중요한 요소로 특징을 알아두면 프로젝트 성격에 최적화할 수 있습니다.

감사합니다.
