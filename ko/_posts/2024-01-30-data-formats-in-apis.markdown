---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Data_Formats_In_APIs
title: API에서의 데이터 형식 이해에 대하여
# title: About understanding data formats in APIs
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Network
# multiple tag entries are possible
tags: [network]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-30 09:00:00 +0900
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

## 개요

API(애플리케이션 프로그래밍 인터페이스)는 소프트웨어 애플리케이션 간에 데이터를 원활하게 교환하기 위한 핵심 요소입니다.

API 작업 시 데이터 형식을 이해하는 것은 매우 중요합니다.

이 글에서는 API 상호작용에서 흔히 사용되는 문자열과 JSON(JavaScript Object Notation) 간의 차이점을 살펴보겠습니다.

<!-- outline-end -->

### 문자열: 기본적인 텍스트 데이터

문자열은 문자의 연속으로 텍스트 데이터를 나타냅니다.

대부분의 프로그래밍 언어에서 기본적인 데이터 유형 중 하나입니다.

API에서는 데이터를 문자열 형식으로 네트워크를 통해 전송하는 경우가 많습니다.

이는 네트워크가 텍스트 데이터와 더 효율적으로 작동하기 때문입니다.

### JSON: 가벼운 데이터 교환

반면에 JSON은 가벼운 데이터 교환 형식입니다.

사람과 기계 모두가 쉽게 읽고 쓸 수 있습니다.

JSON은 데이터 객체를 속성-값 쌍으로 표현하는 구조적인 방법을 제공하며 데이터 교환에 매우 적합합니다.

#### API 응답에서 왜 문자열을 사용하는가?

API가 요청에 응답할 때 일반적으로 데이터를 문자열 형식으로 반환합니다.

이는 네트워크 통신의 특성 때문입니다.

문자열은 네트워크를 통해 전송하기에 더 효율적이며 데이터를 읽을 수 있는 보편적인 형식을 제공합니다.

### JSON 구문 분석: 문자열을 객체로 변환

문자열 형식의 API 응답을 받으면 일반적으로 이를 프로그래밍 언어에서 사용할 수 있는 형식으로 변환해야 합니다.

JavaScript에서는 JSON.parse() 함수를 사용하여 JSON 문자열을 JavaScript 객체나 배열로 변환합니다.

이 구문 분석 단계를 통해 데이터를 효과적으로 활용할 수 있습니다.

#### 실제 예시

금융 시장 데이터를 반환하는 API를 고려해봅시다.

비트코인(BTC)과 같은 암호화폐의 일일 캔들스틱 정보를 반환하는 경우가 있을 것입니다.

응답은 여러 날짜에 대한 시가, 종가, 고가, 저가, 거래량 및 타임스탬프와 같은 세부 정보를 포함하는 JSON 문자열일 것입니다.

```javascript
const apiResponse =
  '[{"market":"KRW-BTC","candle_date_time_utc":"2023-11-15T00:00:00", ... }]';

const parsedData = JSON.parse(apiResponse);
console.log(parsedData);
```

위의 예시에서 parsedData는 이제 JavaScript 객체로 API 응답을 보유하고 있어, 개발자는 trade_price와 같은 특정 데이터 필드에 쉽게 액세스할 수 있습니다.

### 결론

API 상호작용에서 문자열과 JSON 간의 상호작용을 이해하는 것은 효과적인 데이터 교환과 활용을 위해 필수적입니다.

API를 사용하는 애플리케이션을 개발하거나 API를 설계하는 경우, 이러한 데이터 형식의 역할을 인식하면 더 넓은 소프트웨어 생태계 내에서 원활하게 작업할 수 있습니다.
