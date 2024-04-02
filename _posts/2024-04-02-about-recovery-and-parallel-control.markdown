---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Recovery_And_Parallel_Control
title: About recovery and parallel control
# title: About recovery and parallel control
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: DB
# multiple tag entries are possible
tags: [db]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-04-02 09:00:00 +0900
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

## 교착상태와 해결 기법에 대하여 알아본 글입니다.

안녕하세요! 오늘부터는 글의 생기를 불어넣기 위해 매일 조금씩 글의 주제와 상관없는 TMI를 넣어볼까합니다.

**---오늘의 TMI---**

오늘은 저의 26번째 생일입니다.

사실 이것저것 많은 것을 했는데 이 경험들이 제 인생에 도움이 될지 몰라 잠시 생각에 잠겼네요.. 지금은 아무것도 하지 않으면 변하지 않는다는 생각으로 꾸준히 계속 할 생각입니다!

여러분도 의미를 떠나 꾸준히 하고 있는 행동이 있나요? 언제가 될지는 모르지만 인생에 도움이 될 것이라고 생각합니다!

응원하겠습니다!

**---TMI 끝---**

돌아와서 이번에는 컴퓨터 시스템에서 발생할 수 있는 교착상태에 대해 알아보고, 이를 해결하기 위한 기법들에 대해 살펴보겠습니다.

교착상태는 시스템 자원을 요구하며 동시에 점유하고 있는 프로세스들이 서로 필요한 자원을 기다리며 무한히 대기하는 상황을 말합니다.

이러한 상황은 시스템의 작동을 멈추게 할 수 있으므로 중요한 개념입니다.

지금부터 자세히 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 교착상태 발생의 필요충분 조건

- 상호 배제 (Mutual Exclusion) : 자원은 동시에 하나의 프로세스만이 사용할 수 있어야 합니다.
- 점유와 대기 (Hold and Wait) : 프로세스가 최소한 하나의 자원을 점유한 상태에서 다른 자원을 기다리고 있어야 합니다.
- 비선점 (No Preemption) : 다른 프로세스가 이미 점유한 자원을 강제로 빼앗을 수 없어야 합니다.
- 환형 대기 (Circular Wait) : 프로세스의 집합에서 자원을 대기하기 위해 형성된 환형 구조가 존재해야 합니다.

이 네 가지 조건이 동시에 충족될 때 교착상태가 발생할 수 있습니다.

### 교착상태 해결 기법

- 교착상태 예방 (Deadlock Prevention) : 교착상태 발생의 필요충분 조건 중 하나를 제거하여 교착상태를 예방하는 방법입니다. 예를 들어, 자원 할당 순서를 일정하게 정하여 환형 대기 조건을 제거할 수 있습니다.
- 교착상태 회피 (Deadlock Avoidance) : 자원 요청에 대한 부여를 사전에 검사하여 교착상태가 발생하지 않도록 하는 방법입니다. 은행원 알고리즘이 대표적인 예로, 안전 상태를 유지할 수 있는 자원 할당만 허용합니다.
- 교착상태 탐지와 회복 (Deadlock Detection and Recovery): 교착상태가 발생하면 감지하여 회복하는 방법입니다. 자원 할당 그래프 등을 통해 교착상태를 탐지하고, 교착상태에 포함된 프로세스를 중지하거나 자원을 선점하여 회복합니다.
- 교착상태 무시 (Deadlock Ignorance) : 교착상태가 발생할 가능성이 매우 낮거나 발생해도 시스템에 큰 영향을 주지 않는 경우, 교착상태를 무시합니다. 일부 실시간 시스템에서는 교착상태를 무시하는 것이 합리적일 수 있습니다.

## 마치며

교착상태는 시스템의 안정성을 위협하는 중요한 문제입니다.

따라서 시스템 설계자와 개발자들은 교착상태의 발생 가능성을 고려하고, 적절한 교착상태 해결 기법을 선택하여 시스템 안정성을 유지해야 합니다.

이를 통해 교착상태로 인한 잠재적인 문제를 예방하고, 원활한 시스템 운영을 실현할 수 있습니다.
