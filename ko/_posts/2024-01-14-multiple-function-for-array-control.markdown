---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Multiple_Functions_For_Array_Control
title: 배열 제어에 대한 여러 함수 소개에 대하여
# title: About introducing multiple functions for array control
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Javascript
# multiple tag entries are possible
tags: [javascript]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-14 09:00:00 +0900
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

## "문자열 제어에 대한 여러 함수"에 대하여

코딩 테스트를 진행하며, 문자열 제어에 대한 여러 함수가 있다는 것을 알게 되었습니다.

이에 공유하고자 합니다.

{:data-align="center"}

<!-- outline-end -->

### 문자열 대문자와 소문자로 변환하는 방법

toUpperCase() : 영문 문자열에 대하여 대문자로 변환
toLowerCase(): 영문 문자열에 대하여 소문자로 변환

### 정규 표현식에 따른 문자열이 조건 만족하는지 판단하는 방법

regexObj.test(str)를 사용합니다.

주어진 문자열이 정규 표현식을 만족하는지 판별하고, 그 여부를 true 또는 false로 반환합니다.

```javascript
const str = "table football";

const regex = new RegExp("foo*");
// Expected output: true
```

### 문자열에서 백슬래쉬를 활용하는 방법

\": " 쌍 따옴표를 출력
\": ' 작은 따옴표를 출력
\\: \ 문자를 출력
\r: 커서를 해당 줄 처음으로 이동시킴
\f: 커서를 다음 페이지로 이동
\b: 커서를 한 칸 이동시킨다.
\t: 커서를 탭 만큼 이동시킨다.
\n: 커서를 다음 줄로 이동시킨다.

#### 예시

```javascript
var a = "My home is "Seoul"."  : 출력 불가
var a = "My home is \"Seoul"\."  : 출력 가능
```
