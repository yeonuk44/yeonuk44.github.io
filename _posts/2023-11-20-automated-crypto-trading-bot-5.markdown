---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_5
title: Automated crypto trading bot implementation 5 (with.Upbit Open API)
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
date: 2023-11-20 09:00:00 +0900
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

## "자동 암호화폐 매매 봇 구현 4(시리즈)"에 대한 글입니다.

요즘 암호화폐의 가치가 꾸준히 상승장으로 이어지고 있습니다.

상승장에선 각자의 매매기법에 따라 트레이딩을 진행할 필요가 있습니다.

이번 시리즈에선 내가 계속 보지 않아도 코드에 작성된 로직에 따라 자동으로 매매를 진행해주는 트레이딩 봇을 만들어보겠습니다.

이전 글에선 Bollinger Bands가 무엇인지 알아보고 해당 기술적 지표를 코드를 통해 직접 구현하였습니다. 이번 글에선 작성된 코드들에 대해 단계별 가이드를 준비했습니다.

(참고: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

### Bollinger Bands 소개

볼린저 밴드는 존 볼린저(John Bollinger)가 개발한 기술적 분석 도구로, 금융 시장에서 추세, 변동성 및 잠재적인 반전 지점을 식별하는 데 사용되는 인기 있는 도구입니다.

이는 상중하 3개의 밴드로 구성되어 있으며, 중간 밴드는 단순 이동 평균이며 상단 및 하단 밴드는 중간 밴드에서의 표준 편차를 기반으로 계산됩니다.

### Bollinger Bands 이해하기

1. 중간 밴드
   - 중간 밴드는 단순 이동 평균(SMA)으로서 특정 기간 동안의 평균 가격을 나타냅니다.
2. 상단 및 하단 밴드
   - 상단 밴드: 중간 밴드와 표준 편차의 두 배를 더한 값으로 계산됩니다.
   - 하단 밴드: 중간 밴드에서 표준 편차의 두 배를 뺀 값으로 계산됩니다.
   - 이러한 밴드들은 중간 밴드를 중심으로 동적인 범위를 제공하며, 고변동성 기간에는 확장되고 저변동성 기간에는 축소됩니다.

### 차트의 기술적 지표를 코드로 구현하기

```javascript
function bb(tradePrices) {
  const period = 20;
  const movingAverages = [];

  // 이동 평균 계산
  for (let i = 0; i <= tradePrices.length - period; i++) {
    const average =
      tradePrices.slice(i, i + period).reduce((sum, price) => sum + price, 0) /
      period;
    movingAverages.push(average);
  }

  // 표준 편차 계산
  const standardDeviation = Math.sqrt(
    movingAverages.reduce(
      (sum, avg) => sum + Math.pow(avg - movingAverages[0], 2),
      0
    ) / period
  );

  // 볼린저 밴드 계산
  const upperBand = movingAverages[0] + 2 * standardDeviation;
  const middleBand = movingAverages[0];
  const lowerBand = movingAverages[0] - 2 * standardDeviation;

  // 결과를 객체로 저장
  const bollingerBands = {
    "상단 밴드": upperBand,
    "중간 밴드": middleBand,
    "하단 밴드": lowerBand,
  };

  return bollingerBands;
}

module.exports = {
  bb,
};
```

이 구현에서:

movingAverages 배열은 계산된 이동 평균을 저장합니다.

표준 편차는 이동 평균을 기반으로 계산됩니다.

상단 및 하단 밴드는 표준 편차를 사용하여 결정됩니다.
