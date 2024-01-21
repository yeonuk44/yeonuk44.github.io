---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Greedy_Strategy
title: Greedy Strategy(탐욕 알고리즘)에 대하여
# title: About the Greedy Strategy (Greedy Algorithm)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Algorithm
# multiple tag entries are possible
tags: [algorithm]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-21 09:00:00 +0900
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

## "Greedy Strategy(탐욕 알고리즘)"에 대하여

이 글에서는 Greedy Strategy의 개념과 작동 방식, 그리고 어떤 상황에서 유용하게 활용될 수 있는지에 대해 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 소개

Greedy Strategy 또는 탐욕 알고리즘은 알고리즘 이론에서 중요한 역할을 하는 기법 중 하나입니다.

이 기법은 항상 현재 상황에서 최선의 선택을 하는 방식으로 동작하여 최적의 해를 찾는 방법 중 하나입니다.

#### Greedy Strategy란?

Greedy Strategy는 매 순간마다 최적의 선택을 하는 알고리즘입니다.

이는 현재 시점에서의 최선의 선택을 계속해서 반복하며 최종 결과를 얻는 방법입니다. 이 때 선택의 기준은 각 단계에서의 가장 이상적인 선택입니다.

이 선택이 단계별로 최적이라면, 전체적으로도 최적일 것이라는 믿음에 기반합니다.

Greedy Strategy의 핵심은 간단한 규칙을 따르는 것입니다.

매 순간의 최적 선택을 찾아내고, 그 선택이 전체적으로 최적인지 확인하는 것이 중요합니다.

Greedy 알고리즘은 문제를 부분 문제로 나누고, 각 부분 문제에서 최적해를 찾아 전체 문제의 최적해를 구하는 방식으로 작동합니다.

#### Greedy Strategy의 예시

- 거스름돈 문제: 최소한의 동전 개수로 거스름돈을 주는 문제에서, 가장 큰 단위의 동전부터 선택하는 것이 Greedy 알고리즘의 한 예입니다.
- Prim 알고리즘: 최소 신장 트리(Minimum Spanning Tree)를 찾는 Prim 알고리즘은 Greedy 방식을 활용하여 가장 작은 가중치의 간선을 선택하는 과정을 반복합니다.
- Kruskal 알고리즘: 또 다른 최소 신장 트리 알고리즘인 Kruskal 알고리즘은 간선을 가중치 오름차순으로 정렬하고, 사이클을 형성하지 않는 간선을 선택합니다.
- Dijkstra 알고리즘: 최단 경로 문제에서 Dijkstra 알고리즘은 가장 짧은 경로를 선택하는 Greedy 방식을 사용합니다.

#### Greedy Strategy의 한계

Greedy Strategy는 많은 문제에 유용하지만, 모든 문제에 적합한 것은 아닙니다.

Greedy 알고리즘은 각 단계에서의 최적 선택을 찾지만, 그 선택이 전체적으로 최적해를 보장하지는 않습니다.

어떤 문제에서는 Greedy 접근법이 최적해에 수렴하지 않을 수도 있습니다.

이러한 한계를 이해하고, 문제의 특성에 따라 Greedy를 사용할지 결정해야 합니다.

#### 결론

Greedy Strategy는 간단하고 직관적인 방식으로 다양한 문제를 해결할 수 있는 강력한 도구입니다.

하지만 모든 문제에 적용 가능한 것은 아니며, 각 문제의 특성에 따라 최적의 해결 방법을 선택해야 합니다.

Greedy 알고리즘은 단계마다 최적 선택을 찾는 방식으로 동작하므로, 문제를 분해하고 각 부분 문제를 최적화하는데 유용합니다.
