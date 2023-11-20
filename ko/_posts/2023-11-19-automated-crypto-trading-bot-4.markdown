---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_4
title: 자동 암호화폐 매매 봇 구현 4(with.Upbit Open API)
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
date: 2023-11-19 09:00:00 +0900
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

## "자동 암호화폐 매매 봇 구현 3(시리즈)"에 대한 글입니다.

요즘 암호화폐의 가치가 꾸준히 상승장으로 이어지고 있습니다.

상승장에선 각자의 매매기법에 따라 트레이딩을 진행할 필요가 있습니다.

이번 시리즈에선 내가 계속 보지 않아도 코드에 작성된 로직에 따라 자동으로 매매를 진행해주는 트레이딩 봇을 만들어보겠습니다.

이전 글에선 매매를 직접 수행하였으니 이번 글에선 볼린저밴드와 같은 투자 기법을 구현하기 위해 캔들 정보를 가져오고 값을 구하는 것을 진행해보겠습니다.(참고: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

### 캔들 정보 조회 API

Upbit의 캔들 정보 조회 API는 특정 마켓의 캔들 정보를 가져올 수 있습니다. 이를 통해 트렌드 분석, 기술적 분석 등 다양한 목적으로 활용할 수 있습니다.

나의 코드

getDailyCandlesInfo 함수

```javascript
function getDailyCandlesInfo() {
  // API 요청 옵션 설정
  const options = {
    method: "GET",
    url: "https://api.upbit.com/v1/candles/days?count=30&market=KRW-BTC",
    headers: { accept: "application/json" },
  };

  // API 요청 및 응답 처리
  return new Promise((resolve, reject) => {
    request(options, (error, response, body) => {
      if (error) {
        reject(error);
      } else {
        try {
          // JSON 파싱
          const responseBody = JSON.parse(body);

          // 캔들의 거래 가격만 추출
          const tradePrices = responseBody.map((candle) => candle.trade_price);

          // 기술적 분석(Bollinger Bands)을 통한 값 계산
          const dailyBBValue = technicalBollingerBand.bb(tradePrices);

          // 결과 반환
          resolve(dailyBBValue);
        } catch (parseError) {
          reject(parseError);
        }
      }
    });
  });
}
```

상기의 코드는 KRW-BTC 마켓의 일별 캔들의 정보를 QS을 통해 요청하고 받아와 JSON형식으로 파싱하여 원하는 캔들의 종가 가격만을 추출하였습니다.

다음 글에서 사용될 Bollinger Bands의 함수에 삽입해 트레이딩의 기술적 분석 근거를 산출했습니다.

다음은 트레이딩을 위한 1분당 캔들 정보를 구하는 코드입니다.

getMinuteCandleInfo 함수

```javascript
function getMinuteCandleInfo() {
  // API 요청 옵션 설정
  const options = {
    method: "GET",
    url: "https://api.upbit.com/v1/candles/minutes/1?market=KRW-BTC&count=1",
    headers: { accept: "application/json" },
  };

  // API 요청 및 응답 처리
  return new Promise((resolve, reject) => {
    request(options, (error, response, body) => {
      if (error) {
        reject(error);
      } else {
        try {
          // JSON 파싱
          const responseBody = JSON.parse(body);

          // 캔들의 거래 가격만 추출
          const tradePrices = responseBody.map((candle) => candle.trade_price);

          // 결과 반환
          resolve(tradePrices);
        } catch (parseError) {
          reject(parseError);
        }
      }
    });
  });
}
```

위와 같이 작성된 코드를 사용하는 예시도 가져왔습니다.

사용 예시

```javascript
const { getDailyCandlesInfo, getMinuteCandleInfo } = require("./path/to/api");

// 일봉 캔들 정보 조회
getDailyCandlesInfo()
  .then((dailyBBValue) => {
    console.log("일봉 Bollinger Bands 값:", dailyBBValue);
  })
  .catch((error) => {
    console.error("일봉 캔들 정보 조회 실패:", error);
  });

// 1분봉 캔들 정보 조회
getMinuteCandleInfo()
  .then((tradePrices) => {
    console.log("1분봉 거래 가격:", tradePrices);
  })
  .catch((error) => {
    console.error("1분봉 캔들 정보 조회 실패:", error);
  });
```

### 마무리

Upbit의 캔들 정보 조회 API를 활용하면 시장 동향을 파악하고 기술적 분석을 수행하는 데 도움이 됩니다.

위의 함수들을 활용하여 캔들 정보를 가져오고, 필요에 따라 분석하여 투자 결정에 활용할 수 있습니다.

다음 글에선 볼린저밴드와 같은 기술적 분석 지표를 알고리즘을 통해 구현하고 더 나아가 주기적인 API 콜로 투자기법을 적용한 트레이딩 봇을 구현해보도록 하겠습니다.

고생하셨습니다.
