---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Server_Authentication
title: 서버 인증에 대하여
# title: About server authentication
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-04-13 09:00:00 +0900
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

## 서버 인증에 대하여 알아본 글입니다.

안녕하세요!

서버 인증에 대해 알아보려고 하는 분들을 위해 이번에는 인증, 인가, 지식, 소유, 행위 기반 인증에 대해 알아보도록 하겠습니다.

글을 본격적으로 시작하기에 앞서,

**---오늘의 TMI---**

워드프로세스와 컴퓨터 활용 능력 자격증을 취득했습니다!

자습책 및 인강 하나 없이 문제를 보고, 기출문제만 계속 풀이하고 갔는데 필기 및 실기 전부 잘 봐서 붙었습니다!

오늘은 기분 좋은 하루가 되었네요ㅎㅎ 여러분도 좋은 일 가득 하시길 바랍니다!

**---TMI 끝---**

글로 돌아가겠습니다!

서버 인증은 정보 보안에서 매우 중요한 개념이며, 이해하는 것이 중요합니다.

{:data-align="center"}

<!-- outline-end -->

### 인증(Authentication)

인증은 사용자가 자신을 신원을 증명하는 과정입니다.

서버에 접근하려는 사용자는 자신의 신원을 증명하기 위해 주로 아이디와 비밀번호를 제공합니다.

이 정보를 통해 서버는 사용자가 누구인지 확인하고 인증을 완료합니다.

### 인가(Authorization)

인가는 인증된 사용자에게 특정 리소스나 서비스에 접근할 수 있는 권한을 부여하는 과정입니다.

예를 들어, 인증된 사용자가 특정 디렉토리에 접근하거나 파일을 수정할 수 있는지 여부를 결정하는 것이 인가입니다.

### 지식 기반 인증(Knowledge-based Authentication)

지식 기반 인증은 사용자가 미리 정의된 질문에 대한 정확한 답변을 제공하여 신원을 확인하는 방식입니다.

예를 들어, "어린 시절 어디인가요?"와 같은 질문에 정확한 답변을 제공해야 인증이 완료됩니다.

### 소유 기반 인증(Possession-based Authentication)

소유 기반 인증은 사용자가 소유한 물리적인 장치나 미디어를 사용하여 인증하는 방식입니다.

대표적인 예로는 SMS로 전송된 일회용 인증번호를 입력하는 방식이 있습니다.

이 방식은 사용자가 자신의 핸드폰을 소유하고 있다는 것을 확인하여 인증을 완료합니다.

### 행위 기반 인증(Behavior-based Authentication)

행위 기반 인증은 사용자의 특정 행동 패턴을 분석하여 신원을 확인하는 방식입니다.

사용자의 타이핑 스타일, 마우스 사용 패턴, 터치 동작 등을 분석하여 인증을 수행합니다.

이 방식은 사용자의 특징적인 행동을 기반으로 하기 때문에 보안성이 높다고 평가됩니다.

서버 인증은 위에서 소개한 다양한 방식을 조합하여 사용할 수도 있습니다.

예를 들어, 사용자는 아이디와 비밀번호로 인증을 수행한 후에, 추가적인 인증 단계로 SMS로 전송된 일회용 인증번호를 입력하는 방식을 사용할 수 있습니다.

## 마치며

이상으로 서버 인증에 대한 개념을 간략히 소개해드렸습니다.

이해를 돕기 위해 다양한 인증 방식을 포함하여 설명해보았는데요, 보다 안전한 서버 인증을 위해서는 다중 인증 방식을 사용하는 것이 좋습니다.

각각의 인증 방식은 장단점이 있으므로 상황에 맞게 적절히 조합하여 사용하는 것이 중요합니다.

감사합니다.
