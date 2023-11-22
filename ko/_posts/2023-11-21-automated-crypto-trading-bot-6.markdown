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

## "자동 암호화폐 매매 봇 구현 6(시리즈)"에 대한 글입니다.

요즘 암호화폐의 가치가 꾸준히 상승장으로 이어지고 있습니다.

상승장에선 각자의 매매기법에 따라 트레이딩을 진행할 필요가 있습니다.

이번 시리즈에선 내가 계속 보지 않아도 코드에 작성된 로직에 따라 자동으로 매매를 진행해주는 트레이딩 봇을 만들어보겠습니다.

이전 글에선 작성된 코드들에 대해 단계별 가이드를 준비했습니다.

이번 글에선 더 많은 암호화폐를 거래하기 위해 마켓의 정보를 조회하고 그 결과 값을 json 파일에 내보내는 것까지 진행해보겠습니다.

(참고: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

### 마켓 코드 조회

```javascript
const request = require("request");

const options = {
  method: "GET",
  url: "https://api.upbit.com/v1/market/all?isDetails=false",
  headers: { accept: "application/json" },
};

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

이렇게만 해도 불러와집니다.

그러나 저는 모듈화를 사용해 필요할 때만 사용되길 원하기 때문에 새롭게 market.js를 만들고 해당 함수를 내보낼 수 있는 형태로 만들고자 합니다.

### 나의 마켓코드 조회

```javascript
// market.js
const request = require("request");

function getMarketsInfo() {
  const options = {
    method: "GET",
    url: "https://api.upbit.com/v1/market/all?isDetails=false",
    headers: { accept: "application/json" },
  };

  return new Promise((resolve, reject) => {
    request(options, (error, response, body) => {
      if (error) {
        reject(error);
      } else {
        try {
          const responseBody = JSON.parse(body);
          resolve(responseBody);
        } catch (parseError) {
          reject(parseError);
        }
      }
    });
  });
}

module.exports = {
  getMarketsInfo,
};
```

이렇게 하면 해당 함수가 호출될 때 responseBody에서 선언한 대로 json의 형태로 결과를 출력해줍니다.

더 나아가 저는 json으로 파일을 생성해서 결과값을 내보내길 바라기에 이에 맞는 코드 수정을 해보겠습니다.

### JSON 파일 생성 코드

```javascript
const fs = require("fs");
const request = require("request");

function getMarketsInfo() {
  const options = {
    method: "GET",
    url: "https://api.upbit.com/v1/market/all?isDetails=false",
    headers: { accept: "application/json" },
  };

  return new Promise((resolve, reject) => {
    request(options, (error, response, body) => {
      if (error) {
        reject(error);
      } else {
        try {
          const responseBody = JSON.parse(body);

          // JSON 파일 생성
          fs.writeFileSync(
            "marketsInfo.json",
            JSON.stringify(responseBody, null, 2)
          );

          resolve(responseBody);
        } catch (parseError) {
          reject(parseError);
        }
      }
    });
  });
}

module.exports = {
  getMarketsInfo,
};
```

### 마무리

Node.js의 fs 모듈을 이용하면 간단하게 파일 시스템을 다룰 수 있습니다. JSON 파일 생성 외에도 읽기, 업데이트, 삭제 등 다양한 작업을 수행할 수 있으니 필요한 기능에 맞게 활용해보세요.

이상으로 Node.js에서 파일 시스템을 다루는 간단한 예제를 살펴보았습니다. 참고가 되셨기를 바랍니다.
