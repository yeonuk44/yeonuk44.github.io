---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_2
title: 자동 암호화폐 매매 봇 구현 2(with.Upbit Open API)
# title: Automated crypto trading bot implementation 1 (with.Upbit Open API)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: JavaScript
# multiple tag entries are possible
tags: [javascript, network]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-11-17 09:00:00 +0900
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

### "자동 암호화폐 매매 봇 구현 2(시리즈)"에 대한 글입니다.

요즘 암호화폐의 가치가 꾸준히 상승장으로 이어지고 있습니다.

상승장에선 각자의 매매기법에 따라 트레이딩을 진행할 필요가 있습니다.

이번 시리즈에선 내가 계속 보지 않아도 코드에 작성된 로직에 따라 자동으로 매매를 진행해주는 트레이딩 봇을 만들어보겠습니다.

이전 글에선 준비하는 과정 및 프로젝트 세팅까지 진행하였으니 이번 글에선 매매를 직접 진행해보겠습니다.(참고: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

#### 준비물

- 업비트 계정
- 본인의 IP 주소(보안 상 트레이딩 봇을 실행시킬 특정 IP 주소가 필요합니다)

#### 내용

업비트 뿐만 아니라 거래소에서 제공하는 정보를 사용하기 위해선 해당 거래소에서 제공하는 Open API가 존재하는지 알고 있어야 합니다.

해당 글에선 Javascript를 사용하기에 Node.js의 프로젝트 매니저인 npm을 사용하겠습니다.

1. 먼저 업비트 공식 홈페이지에서 고객센터에 있는 OpenAPI 란으로 이동합니다. (참고: https://upbit.com/service_center/open_api_guide)
   이후 로그인을 해서 Open API 사용하기 이후 Open API Key 발급하기를 눌러 발급합니다. 이때 여러분이 트레이딩 봇에서 사용할 기술의 범위를 체크하여 발급합니다.
   저는 다 체크해서 발급했습니다.
2. 프로젝트를 만듭니다.
   폴더를 만들고, 터미널을 통해 Node.js를 설치합니다.
   윈도우라면 공식 웹사이트(참고: https://nodejs.org/en) 에서 설치 프로그램 다운 후 진행하시면 되고, Mac이라면 Homebrew를 통해 brew install node 하시면 됩니다.
   Node.js가 설치되었다면 Node의 패키지 매니저인 npm을 통해 초기 프로젝트 세팅을 해줍니다.

```javascript
npm init -y // 간략 세팅 방법입니다.
```

3. OpenAPI 이용을 위한 라이브러리를 설치해줍니다.

```javascript
npm install request jsonwebtoken
```

4. 프로젝트에 index.js 파일을 만들고 "전체 계좌 조회" API 사용 예시를 업비트 개발자센터에서 불러옵니다.(참고: https://docs.upbit.com/reference/%EC%A0%84%EC%B2%B4-%EA%B3%84%EC%A2%8C-%EC%A1%B0%ED%9A%8C)
   불러온 코드

```javascript
const access_key = process.env.UPBIT_OPEN_API_ACCESS_KEY;
const secret_key = process.env.UPBIT_OPEN_API_SECRET_KEY;
const server_url = process.env.UPBIT_OPEN_API_SERVER_URL;
```

#### 마무리

위와 같이 access_key, secret_key, server_url를 각각 Open API Key 발급받은 대로 입력해주어야 하는데 저의 경우 깃허브에 해당 프로젝트를 올려서 공유할 예정이기에 dependencies에 dotenv 라이브러리를 추가하여 .env 파일로 Key를 관리하고 있습니다.

저와 같이 관리하신다면 gitignore 파일에 .env는 변경사항에서 제외한다는 명령어를 추가해주어야 합니다. 상기의 키를 입력하고 $ node index.js 를 입력하면 잘 실행됩니다.
