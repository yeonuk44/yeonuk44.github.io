---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Hashmap
title: 해시맵(HashMap)에 대하여(with.Java)
# title: Comparing Arrays (with.Java)
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
date: 2023-10-31 09:00:00 +0900
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

### HashMap에 대하여 알아본 글입니다.

코딩테스트를 준비하며, 자바의 유용한 도구가 있어 소개하고자 기록합니다.

{:data-align="center"}

<!-- outline-end -->

#### 해시맵(HashMap)이란?

해시맵(HashMap)은 키-값 쌍을 저장하고, 키를 기반으로 값을 검색하고 조작하는 자료구조입니다. Java에서는 java.util 패키지에 포함되어 있습니다.

#### 해시맵의 주요 특징

- 키-값 쌍 저장: 해시맵은 키와 값을 연결하여 데이터를 저장합니다. 키는 고유하며, 중복되지 않습니다.
- 빠른 검색 속도: 해시맵은 키를 기반으로 값을 검색하므로 데이터를 빠르게 찾을 수 있습니다.
- 순서가 없음: 해시맵은 데이터의 순서를 보장하지 않습니다. 따라서 데이터를 저장한 순서대로 검색되지 않습니다.
- 키 중복 불가: 하나의 해시맵에는 동일한 키가 중복되어 저장될 수 없습니다. 중복된 키를 사용하면 기존 값이 대체됩니다.
- 동기화 지원: 멀티스레드 환경에서 안전하게 사용하려면 Collections.synchronizedMap()을 사용하여 동기화된 해시맵을 만들 수 있습니다.

#### 해시맵에서 자주 사용하는 메서드 정리

- put(key, value): 지정된 키와 값을 매핑하여 해시맵에 추가합니다. 만약 이미 같은 키가 존재한다면, 기존 값은 대체됩니다.
- get(key): 주어진 키에 해당하는 값을 반환합니다. 키가 존재하지 않으면 null을 반환합니다.
- containsKey(key): 지정된 키가 해시맵 내에 존재하는지 여부를 확인합니다. 존재하면 true를 반환하고, 그렇지 않으면 false를 반환합니다.
- containsValue(value): 지정된 값이 해시맵 내에 존재하는지 여부를 확인합니다. 존재하면 true를 반환하고, 그렇지 않으면 false를 반환합니다.
- remove(key): 지정된 키와 연결된 값을 해시맵에서 제거합니다.
- size(): 해시맵에 저장된 키-값 쌍의 개수를 반환합니다.
- isEmpty(): 해시맵이 비어 있는지 여부를 확인합니다. 비어 있으면 true를 반환하고, 그렇지 않으면 false를 반환합니다.
- clear(): 해시맵 내의 모든 키-값 쌍을 제거하여 비웁니다.
- keySet(): 해시맵의 모든 키를 포함하는 Set 컬렉션을 반환합니다. 이를 통해 모든 키에 접근할 수 있습니다.
- values(): 해시맵의 모든 값을 포함하는 Collection을 반환합니다. 이를 통해 모든 값을 열거할 수 있습니다.
- entrySet(): 해시맵의 키-값 쌍을 포함하는 Set 컬렉션을 반환합니다. 이를 통해 모든 키-값 쌍에 접근할 수 있습니다.

#### 정리

즉, 해시맵은 다양한 자바 컬렉션 프레임워크 클래스 중 하나로, 특히 데이터를 효과적으로 저장하고 검색해야 하는 상황에서 유용하게 사용됩니다.
