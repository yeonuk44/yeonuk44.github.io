---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_6
title: 자동 암호화폐 매매 봇 구현 6(with.Upbit Open API)
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
date: 2023-11-21 09:00:00 +0900
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

## "자동 암호화폐 매매 봇 구현 5(시리즈)"에 대한 글입니다.

요즘 암호화폐의 가치가 꾸준히 상승장으로 이어지고 있습니다.

상승장에선 각자의 매매기법에 따라 트레이딩을 진행할 필요가 있습니다.

이번 시리즈에선 내가 계속 보지 않아도 코드에 작성된 로직에 따라 자동으로 매매를 진행해주는 트레이딩 봇을 만들어보겠습니다.

이전 글에선 Bollinger Bands가 무엇인지 알아보고 해당 기술적 지표를 코드를 통해 직접 구현하였습니다. 이번 글에선 작성된 코드들에 대해 단계별 가이드를 준비했습니다.

(참고: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

### 필수 모듈 설치

```javascript
npm install request
npm install uuid
npm install crypto
npm install jsonwebtoken
npm install querystring
npm install dotenv
```

### API 키 및 시크릿 설정

Upbit Open API를 사용하기 위해 Upbit 개발자 센터에서 API 키와 시크릿을 발급받아 .env 파일에 저장하세요.

```javasciprt
UPBIT_OPEN_API_ACCESS_KEY=your_access_key
UPBIT_OPEN_API_SECRET_KEY=your_secret_key
UPBIT_OPEN_API_SERVER_URL=https://api.upbit.com
```

### 필수 파일 및 모듈 로드

```javascript
const request = require("request");
const uuidv4 = require("uuid/v4");
const crypto = require("crypto");
const sign = require("jsonwebtoken").sign;
const queryEncode = require("querystring").encode;
const dotenv = require("dotenv");
const accountsInfo = require("./apis/assets");
const orderCryptocurrency = require("./apis/order");
const getCandlesInfo = require("./apis/ticker");

dotenv.config();
```

### 필요한 함수 구현

findKRW 및 findBTC: KRW 및 BTC의 인덱스를 찾는 함수

fetchData: 데이터를 수집하고 매매 전략을 실행하는 메인 함수

해당 글의 개요의 첨부된 코드 저장소를 참고 부탁드립니다.

```javascript
async function findKRW() {
  // ...
}

async function findBTC() {
  // ...
}

async function fetchData() {
  try {
    // ...
  } catch (error) {
    console.error(error);
  }
}

fetchData();
```

### 주기적인 API 호출 및 매매 전략 실행

```javascript
const minuteInterval = setInterval(async () => {
  // ...
}, 60000);
```

### 매매 전략 구현

이 예제에서는 볼린저 밴드를 이용한 간단한 매매 전략을 사용합니다.

```javascript
if (minuteCandlePrice <= lowerBand * 1.05) {
  // 매수 주문 로직
} else if (minuteCandlePrice >= upperBand * 0.95) {
  // 매도 주문 로직
}
```

제가 작성한 자동 암호화폐 매매 봇 시리즈물을 정독하셨다면 어떤 투자 기술 지표를 활용했는지 알 수 있습니다.

### 보완 및 추가 작업

이 프로젝트를 확장하려면 다음과 같은 작업을 고려할 수 있습니다.

전략 최적화: 현재 전략은 간단하게 구현되었지만, 더 복잡한 전략을 구현하여 수익을 극대화할 수 있습니다.

### 마무리

이러한 단계를 참고하여 자동 매매 봇을 개발하면서 JavaScript 및 암호화폐 거래에 대한 이해를 높일 수 있을 것입니다.

부족한 부분은 이메일로 연락주시면 답변을 드리겠습니다.
