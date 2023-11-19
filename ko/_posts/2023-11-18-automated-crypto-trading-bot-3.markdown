---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_3
title: 자동 암호화폐 매매 봇 구현 3(with.Upbit Open API)
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
date: 2023-11-18 09:00:00 +0900
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

## "자동 암호화폐 매매 봇 구현 2(시리즈)"에 대한 글입니다.

요즘 암호화폐의 가치가 꾸준히 상승장으로 이어지고 있습니다.

상승장에선 각자의 매매기법에 따라 트레이딩을 진행할 필요가 있습니다.

이번 시리즈에선 내가 계속 보지 않아도 코드에 작성된 로직에 따라 자동으로 매매를 진행해주는 트레이딩 봇을 만들어보겠습니다.

이전 글에선 준비하는 과정 및 프로젝트 세팅까지 진행하였으니 이번 글에선 매매를 직접 진행해보겠습니다.(참고: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

### 주문 API 사용 방법 (Upbit Open API)

Upbit의 주문 API는 사용자가 지정한 마켓에 대한 주문을 생성하고, 주문을 조회하는 데 사용됩니다. 주문을 생성할 때는 주문 종류(side), 주문량(volume), 주문 가격(price), 주문 타입(ord_type) 등을 지정해야 합니다.

### 주문 API 요청 구성

- URL: 주문 API의 엔드포인트는 /v1/orders입니다.
- Method: 주문을 생성할 때는 POST 메서드를 사용합니다.

### 주요 파라미터

- market (필수): 거래할 암호화폐의 마켓 ID를 지정합니다. 예를 들어, "KRW-BTC"는 한국 원화(KRW)로 비트코인(BTC)을 거래하는 마켓을 의미합니다.
- side (필수): 주문 종류를 나타내는 파라미터입니다.
- bid: 매수 주문 (Buy)
- ask: 매도 주문 (Sell)
- volume: 주문량을 나타냅니다. 매수 주문 시 필수입니다.
- price: 주문 가격을 나타냅니다. 지정가 주문(ord_type: limit) 또는 시장가 매수 주문(ord_type: price) 시 필수입니다.
- ord_type (필수): 주문 타입을 나타냅니다.
- limit: 지정가 주문
- price: 시장가 주문 (매수)
- market: 시장가 주문 (매도)
- identifier: 조회용 사용자 지정값으로 선택적으로 사용됩니다.

### 서명 생성

주문 API를 사용하기 위해서는 API 키 (access_key), API 시크릿 (secret_key)가 필요합니다.
API 요청에 대한 보안을 위해 서명(signature)을 생성해야 합니다.
access_key, nonce, query_hash, query_hash_alg를 조합하여 서명을 생성합니다.
서명은 JWT(JSON Web Token) 형식으로 생성되며, 요청의 Authorization 헤더에 포함됩니다.

### 참고 예시

```javascript
const request = require("request");
const uuidv4 = require("uuid/v4");
const crypto = require("crypto");
const sign = require("jsonwebtoken").sign;
const queryEncode = require("querystring").encode;
const dotenv = require("dotenv");
dotenv.config();

const access_key = process.env.UPBIT_OPEN_API_ACCESS_KEY;
const secret_key = process.env.UPBIT_OPEN_API_SECRET_KEY;
const server_url = process.env.UPBIT_OPEN_API_SERVER_URL;

/*
INFO:
Request Parameters
Name	설명	타입
market *	마켓 ID (필수)	String
side *	주문 종류 (필수)
- bid : 매수
- ask : 매도	String
volume *	주문량 (지정가, 시장가 매도 시 필수)	NumberString
price *	주문 가격. (지정가, 시장가 매수 시 필수)
ex) KRW-BTC 마켓에서 1BTC당 1,000 KRW로 거래할 경우, 값은 1000 이 된다.
ex) KRW-BTC 마켓에서 1BTC당 매도 1호가가 500 KRW 인 경우, 시장가 매수 시 값을 1000으로 세팅하면 2BTC가 매수된다.
(수수료가 존재하거나 매도 1호가의 수량에 따라 상이할 수 있음)	NumberString
ord_type *	주문 타입 (필수)
- limit : 지정가 주문
- price : 시장가 주문(매수)
- market : 시장가 주문(매도)	String
identifier	조회용 사용자 지정값 (선택)	String (Uniq 값 사용)
*/

const body = {
  market: "KRW-BTC",
  side: "bid",
  //   volume: "0.01",
  price: "5000",
  ord_type: "price",
};

const query = queryEncode(body);

const hash = crypto.createHash("sha512");
const queryHash = hash.update(query, "utf-8").digest("hex");

const payload = {
  access_key: access_key,
  nonce: uuidv4(),
  query_hash: queryHash,
  query_hash_alg: "SHA512",
};

const token = sign(payload, secret_key);

function orderCryptocurrency() {
  const options = {
    method: "POST",
    url: server_url + "/v1/orders",
    headers: { Authorization: `Bearer ${token}` },
    json: body,
  };

  return new Promise((resolve, reject) => {
    request(options, (error, response, body) => {
      if (error) {
        reject(error);
      } else {
        resolve(body);
      }
    });
  });
}

module.exports = {
  orderCryptocurrency,
};
```

### 주문 실행 함수

해당 코드에서는 Upbit Open API를 활용하여 주문을 실행하는 함수인 orderCryptocurrency를 정의하고 있습니다. 이 함수는 아래와 같은 기능을 수행합니다.

- 주문에 필요한 파라미터를 설정합니다.
- 파라미터를 이용하여 서명을 생성합니다.
- API 요청을 위한 옵션을 설정합니다.
- API 요청을 수행하고, 결과를 반환합니다.

### 해당 주문 실행 함수의 사용 예시

```javascript
const { orderCryptocurrency } = require("./path/to/orderCryptocurrency");

// 주문 실행
orderCryptocurrency()
  .then((result) => {
    console.log("주문 결과:", result);
  })
  .catch((error) => {
    console.error("주문 실패:", error);
  });
```
