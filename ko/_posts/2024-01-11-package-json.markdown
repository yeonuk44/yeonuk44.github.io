---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_package_json
title: package.json에 대하여
# title: About package.json
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
date: 2024-01-11 09:00:00 +0900
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

## "package.json"에 대하여

오늘은 파일 병합 시 발생할 수 있는 install 에러에 대해 저의 경험을 토대로 글을 작성하고자 합니다.

의존성 모듈을 타 팀원과 일치시킬 필요가 있을 경우 package.json 파일을 교체하는 경우가 있는데요.

물론 git을 통해 협업 환경이 구축되어 있다면 다른 좋은 선택지도 있겠지만 최선으로 행할 수 없을 경우 차선책으로 가야할 때가 있죠.

그런 상황이라고 가정해보겠습니다.

그런데 저의 경우에 project 내부에 package.json에 나오는 의존성 패키지들이 npm install command를 입력할 시 다 설치되어야 하는데 가끔 수동으로 직접 설치해줘야 하는 경우가 있더라고요.

오늘은 이 이슈에 대해 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 왜 가끔 수동으로 설치해줘야 할까요?

1. package.json 파일이 변경되었지만 npm install을 실행하지 않았을 경우: package.json 파일에 의존성 패키지가 추가되거나 업데이트되었을 경우, 해당 변경 사항을 적용하기 위해 npm install을 실행해야 합니다. package.json 파일을 변경한 후에는 npm install 명령어를 다시 실행하여 패키지를 설치해야 합니다.
2. node_modules 디렉토리가 삭제되었을 경우: npm install 명령어를 실행하면 패키지들은 node_modules 디렉토리에 설치됩니다. 만약 node_modules 디렉토리가 수동으로 삭제되었다면, 다시 npm install을 실행하여 패키지를 다시 설치해야 합니다.
3. package-lock.json 파일 충돌: package-lock.json 파일은 패키지 의존성의 정확한 버전을 기록하는 데 사용됩니다. 프로젝트를 공유하거나 협업할 때 다른 개발자가 package-lock.json 파일을 변경하거나 충돌이 발생할 수 있습니다. 이 경우에는 npm install 명령어를 실행하기 전에 package-lock.json 파일을 업데이트하거나 삭제한 후에 실행해야 합니다.
4. 네트워크 문제: 때로는 네트워크 연결 문제로 인해 패키지를 다운로드할 수 없는 경우가 있을 수 있습니다. 이 경우에는 네트워크 연결을 확인하고 npm install을 다시 실행해 보는 것이 좋습니다.

이러한 이유로 인해 의존성 패키지들이 자동으로 설치되지 않을 수 있습니다.

위의 상황 중 하나에 해당하는 경우에는 해당 문제를 해결하기 위해 수동으로 패키지를 설치해야 합니다.

### 결론

이러한 이유로 인해 의존성 패키지들이 자동으로 설치되지 않을 수 있습니다.

위의 상황 중 하나에 해당하는 경우에는 해당 문제를 해결하기 위해 수동으로 패키지를 설치해야 합니다.
