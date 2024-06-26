---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_When_AOS_Development
title: AOS 개발 시, 언어 선택에 대하여
# title: About browser

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Application
# multiple tag entries are possible
tags: [application, kotlin, java]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-07-28 09:00:00 +0900
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

### AOS 개발 시, 언어 선택에 대해 고찰하고 과정을 공유하는 글입니다.

{:data-align="center"}

<!-- outline-end -->

이번에 앱 개발을 맡게 되어 우선적으로 AOS를 학습하고 있습니다.
AOS의 경우 크게 2가지 언어 중 하나로 개발이 이뤄집니다. 바로 Java와 Kotlin입니다.
기존의 저희 앱은 Java를 통해 웹뷰로 구성되었는데 저는 Kotlin을 학습하고 있습니다.
왜냐하면 Kotlin 코드로 리팩토링을 생각하고 있기 때문입니다. 이렇게 결정하게 된 이유에 대해 글로 정리하여 회고하고자 합니다.

안드로이드 앱을 만들 시, 각 언어의 장단점을 분석했습니다.

우선 Java에 대해서 입니다.

#### Java의 장점

- 안드로이드 생태계의 선호 언어: 오랜 기간 동안 안드로이드 앱 개발을 위해 주로 사용되어 왔습니다.
- 다양한 리소스: 많은 개발 도구, 라이브러리, 프레임워크, 문서 등이 Java 기반으로 구축되어 있습니다.
- 커뮤니티 지원: Java로 개발된 안드로이드 앱들에 대한 문제 해결 및 지원이 많이 이루어져 있습니다.
- 크로스 플랫폼 개발: Java는 안드로이드 뿐만 아니라 다른 플랫폼에서도 사용되는 언어이므로, 크로스 플랫폼 개발에 유용합니다.

#### Java의 단점

- 코드 양이 많음: Java는 Kotlin보다 문법이 복잡하고 코드 양이 많을 수 있습니다.
- Null 안정성 부족: Java에서는 null 처리에 대한 지원이 부족하며, NullPointerException 발생 가능성이 높을 수 있습니다.

다음은 Kotlin에 대해서 입니다.

#### Kotlin의 장점

- 간결하고 효율적인 문법: Kotlin은 더 간결하고 효율적인 문법을 갖추고 있어 개발 생산성을 향상시킵니다.
- Null 안정성: Kotlin은 Nullable과 Non-Nullable 타입을 명확하게 지원하여 안정성을 높입니다.
- 자바와 상호 운용성: Kotlin은 기존의 Java 코드와 호환성이 높고, 자바 라이브러리를 쉽게 사용할 수 있습니다.
- 안드로이드 공식 지원: Kotlin은 구글에서 안드로이드 공식 언어로 지정하여 지원과 최적화가 강화되고 있습니다.

#### Kotlin의 단점

- 비교적 새로운 언어: Java에 비해 Kotlin은 상대적으로 새로운 언어이기 때문에, 개발자들이 익숙해지는 시간이 필요할 수 있습니다.
- 빌드 시간: Kotlin은 빌드 시간이 길 수 있으며, 큰 프로젝트에서 빌드 속도가 느려질 수 있습니다.

#### 결론

최종적으로 언어 선택은 개발자의 선호도와 프로젝트 요구 사항에 따라 달라집니다.
Kotlin은 대부분의 측면에서 Java보다 우수한 언어로 인정받고 있으며, 안드로이드 개발을 위한 첫 번째 선택으로 많이 사용되고 있습니다.
하지만 기존에 Java로 개발된 프로젝트를 유지 보수해야 할 때는 Java를 선택하는 것도 합리적일 수 있습니다.

그래서 저희 프로젝트는 안드로이드 개발이 Java로 되어 있으나 웹뷰로만 구현되어 있는 상태이고, 앱개발자도 따로 없기에 처음부터 학습하면 되는 상황입니다.
유지보수할 코드의 양이 비교적 적다는 점과 합쳐져 리스크가 거의 없는 코드 리팩토링을 결정하게 되었습니다.
