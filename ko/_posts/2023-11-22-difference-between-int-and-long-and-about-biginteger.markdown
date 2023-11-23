---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Difference_Between_Int_And_Long_and_About_BigInteger
title: int와 long의 차이 그리고 BigInteger에 대하여(with.Java)
# title: Difference between int and long and about BigInteger (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-11-22 09:00:00 +0900
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

## "int와 long의 차이 그리고 BigInteger에 대하여" 문제에 대하여 알아본 글입니다.

코딩테스트의 문제를 풀며 접했던 데이터 타입에 대해 개략적으로 알고 있었던 정보를 꽤 상세하게 알아볼 수 있었습니다.

이에 이 글을 통해 공유하고자합니다.

{:data-align="center"}

<!-- outline-end -->

### int와 long 데이터타입의 공통점

long과 int는 Java에서 정수 값을 저장하는 데 사용되는 데이터 타입입니다.

#### int와 long 데이터타입의 차이점

1. 범위 (Range):

   - int: 32비트 정수를 나타냅니다. 부호 있는 정수로 약 -2,147,483,648부터 2,147,483,647까지의 범위를 가집니다.
   - long: 64비트 정수를 나타냅니다. 부호 있는 정수로 약 -9,223,372,036,854,775,808부터 9,223,372,036,854,775,807까지의 범위를 가집니다. 이 범위는 int의 범위보다 훨씬 큽니다.

2. 메모리 사용 (Memory Usage):

   - int는 4바이트(32비트)의 메모리를 사용합니다.
   - long은 8바이트(64비트)의 메모리를 사용합니다. 따라서 long 변수는 두 배의 메모리를 차지합니다.

3. 사용 사례:

   - int는 대부분의 상황에서 충분히 사용됩니다. 예를 들어, 배열 인덱스, 반복 변수, 계산 결과 등에 사용됩니다.
   - long은 매우 큰 정수 값을 다루거나 정밀도가 높은 계산이 필요한 경우에 사용됩니다. 시간을 나타내거나 대용량 데이터베이스의 식별자를 다루는 데에도 사용됩니다.

#### 요약

int는 일반적인 정수 연산에 사용되고, 대부분의 상황에서 충분합니다. 그러나 매우 큰 정수 값을 다뤄야하거나 정밀한 계산이 필요한 경우 long을 사용할 수 있습니다.

만약 long데이터 타입으로도 처리되지 않는 64비트를 초과하는 정수의 값은 어떻게 다루면 좋을까요. 이때 사용되는 것이 BigInteger 클래스입니다.

### long과 BigInteger의 공통점

long과 BigInteger는 모두 정수를 다루는 자료형입니다.

### long과 BigInteger의 차이점

1. 크기 한계:

   - long: long은 64비트 부호 있는 정수 자료형으로, 대부분의 상황에서 충분한 범위를 가지고 있습니다. 최소값은 -9,223,372,036,854,775,808이고 최대값은 9,223,372,036,854,775,807입니다. 이 범위 내의 정수만 다룰 수 있습니다.
   - BigInteger: BigInteger는 정밀도 제한이 없는 임의 정밀도 정수를 나타냅니다. 즉, 어떤 크기의 정수도 다룰 수 있으며 제한이 없습니다. 따라서 아주 큰 정수나 정밀도가 필요한 경우에 사용됩니다.

2. 정확성:

   - long: long은 정밀도가 제한되어 있어 큰 정수나 아주 작은 소수를 정확하게 나타낼 수 없을 때 정확성 문제가 발생할 수 있습니다.
   - BigInteger: BigInteger는 정밀도가 제한되어 있지 않으므로 아주 큰 정수나 정밀한 연산을 정확하게 수행할 수 있습니다.

3. 사용법

   - long: long은 기본 자료형으로, 기본 연산자를 사용하여 일반적인 정수 연산을 수행할 수 있습니다.
   - BigInteger: BigInteger는 객체이므로 연산을 수행할 때에는 메서드 호출을 통해 이루어집니다. BigInteger 객체를 생성하고, add, subtract, multiply, divide 등의 메서드를 사용하여 연산을 수행합니다.

#### 요약

long은 대부분의 경우 충분한 정밀도를 제공하며, BigInteger는 아주 크거나 정확한 정수가 필요한 경우에 사용됩니다. 개발 중에 필요한 상황에 맞게 적절한 자료형을 선택해야 합니다.
