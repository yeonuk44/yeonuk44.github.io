---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Type_Conversion
title: 형 변환(Type Conversion)에 대하여
# title: About Type Conversion

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Formatting
# multiple tag entries are possible
tags: [formatting]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-07-19 09:00:00 +0900
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

### 형변환에 대해 알아본 글입니다.

{:data-align="center"}

<!-- outline-end -->

저희 회사에서 이번에 eslint의 조건을 강하게 줘서 코드 포맷팅을 해줘야 하는 상황이 왔는데요.
그 중 "Redundant double negation.eslintno-extra-boolean-cast" 문장을 가장 많이 마주했습니다.

저 에러는 무엇이고, 왜 뜨는 것이고 해결책은 무엇인지 알아보겠습니다.

#### "Redundant double negation.eslintno-extra-boolean-cast" 에러는 무엇인가?

eslint 사용 시, 보일 수 있는 "Redundant double negation.eslintno-extra-boolean-cast" 는 흔히
"no-extra-boolean-cast"라는 규칙으로 알려져 있습니다. 이 규칙은 불필요한 두 번의 부정 연산을 감지하고 경고를 표시합니다.

```javascript
if (!!value) {
  // ...
}
```

이런 코드에서 볼 수 있는 문구입니다.
어떤 문구인지는 알았습니다.

#### 왜 뜨는 걸까요?

위의 예제에서 볼 수 있듯 '!!value"는 불리언 값 'value'를 강제로 부정 연산한 후, 다시 부정 연산을 수행하는 것으로 2번 반복합니다.
이는 형변환의 형태로 사용되고 우리에게 이해되지만 eslint가 권장하는 포맷 형식에는 불필요하며, 코드를 더 복잡하게 만들고 가독성을 낮춘다고 판단합니다.

이제 왜 저런 문구가 뜨는지 알았습니다. 그렇다면 어떻게 해결할 수 있을지 알아보겠습니다.

#### 해결책

위의 문구는 설명한대로 불필요하기 때문에 eslint에서는 제거하도록 권장합니다.
아래와 같이 말이죠.

```javascript
if (value) {
  // ...
}
```

위의 수정된 코드는 'value'를 그대로 사용하여 조건을 평가합니다. 따라서 불필요한 부정 연산을 제거하고 코드를 더 간결하게 만듭니다.

#### 참고

eslint를 사용하여 코드를 정적으로 분석할 때, "Redundant double negation" 규칙이 적용되어 이와 유사한 불필요한 부정 연산을 감지할 수 있습니다.
이 규칙을 적용하면 코드의 가독성을 높이고, 잠재적인 버그를 방지할 수 있습니다.
