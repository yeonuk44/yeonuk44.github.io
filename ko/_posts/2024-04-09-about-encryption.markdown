---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Encryption
title: 암호화에 대하여
# title: About encryption
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development, algorithm]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-04-09 09:00:00 +0900
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

## 캡슐화와 접근 지정자에 대하여 알아본 글입니다.

안녕하세요!

오늘은 객체 지향 프로그래밍에서 중요한 개념인 캡슐화(Encapsulation)와 접근 지정자(Access Modifiers)에 대해 알아보려고 합니다.

글을 본격적으로 시작하기에 앞서,

**---오늘의 TMI---**

어제 먹었던 돼지 후라이드 리뷰입니다! 갈비가 엄청 부드러워서 맛있는데 조금 물리더라고요ㅎㅎ 튀김 옷은 치킨처럼 되어있어서 먹기 좋았습니다! 양념이랑 먹으면 훨씬 맛있었으니, 다음에 또 먹게 된다면 양념 버전으로 먹을 것 같습니다!

오늘 점심은 삼 형제의 손칼국수 집에서 비빔 칼국수와 치즈돈가스를 먹었는데 너무 맛있더라고요! 여러분도 비빔 칼국수 기회가 되면 꼭 드셔보세요ㅎㅎ 식감이 괜찮더라고요!

**---TMI 끝---**

글로 돌아가겠습니다!

{:data-align="center"}

<!-- outline-end -->

### 캡슐화

캡슐화는 객체 지향 프로그래밍의 핵심 개념 중 하나로, 데이터와 해당 데이터를 처리하는 메소드를 하나의 단위로 묶는 것을 의미합니다.

이를 통해 데이터의 은닉성과 보안성을 강화할 수 있습니다.

캡슐화는 클래스를 설계할 때 중요한 역할을 합니다.

클래스는 속성(데이터)과 기능(메소드)을 포함하는데, 이러한 속성과 기능을 외부로부터 감추는 것이 캡슐화의 핵심 아이디어입니다

이는 데이터를 직접 조작하거나 변경하지 않고도 메소드를 통해 간접적으로 데이터에 접근하고 조작할 수 있도록 해줍니다.

### 접근 지정자

접근 지정자는 캡슐화를 구현하기 위한 도구로, 클래스의 멤버(속성과 메소드)에 대한 접근 권한을 제어하는 역할을 합니다.

주요한 접근 지정자로는 public, private, protected 등이 있습니다.

- public: 어떤 클래스든 이 멤버에 접근할 수 있습니다.
- private: 같은 클래스 내에서만 이 멤버에 접근할 수 있습니다.
- protected: 같은 클래스 내부와 동일한 패키지, 그리고 상속 관계에 있는 서브클래스에서 이 멤버에 접근할 수 있습니다.

접근 지정자를 사용하여 멤버의 접근 범위를 제한함으로써, 클래스의 내부 구현을 외부로부터 숨길 수 있습니다.

이는 데이터의 은닉성을 보장하고, 외부에서의 부적절한 접근과 변경을 방지합니다.

또한, 접근 지정자를 통해 캡슐화된 멤버에 대한 접근과 사용을 명확하게 제어할 수 있습니다.

## 마치며

캡슐화와 접근 지정자는 객체 지향 프로그래밍의 핵심 개념으로, 코드의 가독성과 유지 보수성을 향상시키는 중요한 도구입니다.

캡슐화를 통해 데이터와 기능을 하나의 단위로 묶고, 접근 지정자를 사용하여 멤버의 접근 범위를 명확하게 제어함으로써 안전하고 효율적인 프로그램을 작성할 수 있습니다.

이상으로 오늘은 캡슐화와 접근 지정자에 대해 알아보았습니다.

객체 지향 프로그래밍에서 이러한 개념은 중요하며, 잘 이해하고 활용함으로써 품질 좋은 소프트웨어를 개발할 수 있습니다.

감사합니다.
