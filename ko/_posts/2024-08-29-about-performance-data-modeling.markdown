---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Performance_Data_Modeling
title: 성능 데이터 모델링에 대하여
# title: About performance data modeling
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
date: 2024-08-29 09:00:00 +0900
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

## 성능 데이터 모델링에 대하여 알아본 글입니다.

안녕하세요!

오늘은 데이터베이스에서 사용되는 식별자의 특징에 대해 알아보겠습니다.

식별자는 데이터베이스에서 각 행을 고유하게 식별하는 데 사용되는 중요한 요소로, 다음과 같은 특징을 갖고 있어야 합니다.

{:data-align="center"}

<!-- outline-end -->

## 유일성 (Uniqueness)

### 개요

유일성은 각 식별자 값이 고유하다는 것을 의미합니다.

즉, 동일한 값이 두 번 이상 나타나지 않아야 합니다.

### 예시

각 학생의 학번이나 각 제품의 고유한 제품 코드는 유일해야 합니다.

## 최소성 (Minimality)

### 개요

최소성은 식별자가 가능한 한 작고 간결해야 한다는 것을 의미합니다.

즉, 필요한 만큼만 식별자를 사용하여 데이터를 식별해야 합니다.

### 예시

학생을 고유하게 식별하는 데 필요한 최소한의 정보만을 사용하여 학번을 식별자로 선택하는 것이 좋습니다.

학번 외에 학생의 이름이나 주소 등을 추가적으로 사용할 필요는 없습니다.

## 불변성 (Immutability)

### 개요

불변성은 식별자 값이 변하지 않아야 한다는 것을 의미합니다.

즉, 한 번 지정된 식별자 값은 변경되지 않아야 합니다.

### 예시

학생의 학번이나 제품의 제품 코드는 한 번 생성된 후에는 변경되지 않아야 합니다.

## 마치며

식별자는 데이터베이스에서 각 행을 고유하게 식별하는 데 사용되는 중요한 요소입니다.

이러한 식별자는 유일성, 최소성, 불변성 등의 특징을 갖고 있어야 데이터베이스의 정확성과 일관성을 보장할 수 있습니다.

데이터베이스 설계 시 이러한 특징을 고려하여 식별자를 선택하고 관리하는 것이 중요합니다.

이번 포스팅이 식별자의 특징에 대해 이해하는 데 도움이 되었기를 바랍니다.

다음 포스팅에서는 식별자의 종류와 사용 방법에 대해 더 자세히 살펴보겠습니다.

함께 공부해 나가요!
