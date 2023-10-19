---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_StringBuilder
title: StringBuilder가 왜 효율적인가
# title: Why StringBuilder is efficient
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-10-18 09:00:00 +0900
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

### StringBuilder가 왜 효율적인가에 대하여 알아본 글입니다.

우리가 Java로 코딩테스트 문제를 풀거나 프로그래밍 교재를 참고하면 Java와 문자열 조작에 관한 프로그래밍에 대하여 교재는 StringBuilder와 문자열 조작의 이점을 다루는 경우가 많습니다.

이번 글에선 왜 효율적인지에 대해 알아보고 사용하고자 합니다.

{:data-align="center"}

<!-- outline-end -->

#### 왜 사용해야 하는 것이 좋은가?

1. 가변성: StringBuilder는 가변 객체입니다. 이것은 문자열을 수정할 때 새로운 문자열을 계속해서 생성하는 것이 아니라, 원래 문자열을 직접 수정할 수 있다는 것을 의미합니다. 이로 인해 문자열 수정 작업이 빠르고 메모리를 효율적으로 사용할 수 있습니다.
2. 높은 성능: 문자열 수정 시 StringBuilder를 사용하면 매번 새로운 문자열을 생성하거나 복사하는 비용이 들지 않습니다. 그 대신에 기존 문자열을 직접 수정하기 때문에 더 빠른 성능을 제공합니다.
3. 메모리 효율성: StringBuilder는 문자열 조작을 위한 임시 객체를 생성하거나 복사하지 않으므로 메모리를 효율적으로 사용할 수 있습니다.

#### 결론

문자열을 동적으로 조작해야 할 때 StringBuilder를 사용하면 성능과 메모리 사용량 면에서 이점을 얻을 수 있습니다.

반면에 문자열 조작이 빈번하지 않은 경우에는 단순한 문자열 연결(+ 연산자)을 사용해도 큰 문제가 없을 수 있습니다.
