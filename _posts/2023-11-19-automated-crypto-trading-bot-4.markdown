---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_4
title: Automated crypto trading bot implementation 4 (with.Upbit Open API)
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

## This post is about "Implementing an automated cryptocurrency trading bot 4 (series)".

Nowadays, the value of cryptocurrencies is steadily increasing.

In a bull market, it is necessary to trade according to your own trading technique.

In this series, we will create a trading bot that will automatically execute trades based on the logic written in the code without me having to keep an eye on it.

In the previous article, we learned how to get candle information and get values. In this article, we will learn what Bollinger Bands are and implement this technical indicator in code.

{:data-align="center"}

<!-- outline-end -->

### Introduction to Bollinger Bands

Bollinger Bands is a technical analysis tool developed by John Bollinger and is a popular tool used to identify trends, volatility, and potential reversal points in financial markets.

It consists of three bands, the middle band is a simple moving average and the upper and lower bands are calculated based on the standard deviation from the middle band.

### Understanding Bollinger Bands

1. the middle band
   - The middle band is a simple moving average (SMA) and represents the average price over a certain period of time.
2. upper and lower bands
   - Upper Band: Calculated as the middle band plus twice the standard deviation.
   - Bottom band: Calculated as the middle band minus twice the standard deviation.
   - These bands provide a dynamic range centered on the middle band, expanding during periods of high volatility and contracting during periods of low volatility.

### Implementing technical indicators on charts in code

```javascript
function bb(tradePrices) {
  const period = 20;
  const movingAverages = [];

  // calculate moving averages
  for (let i = 0; i <= tradePrices.length - period; i++) {
    const average =
      tradePrices.slice(i, i + period).reduce((sum, price) => sum + price, 0) /
      period;
    movingAverages.push(average);
  }

  // calculate the standard deviation
  const standardDeviation = Math.sqrt(
    movingAverages.reduce(
      (sum, avg) => sum + Math.pow(avg - movingAverages[0], 2),
      0
    ) / period
  );

  // Compute the Bollinger bands
  const upperBand = movingAverages[0] + 2 * standardDeviation;
  const middleBand = movingAverages[0];
  const lowerBand = movingAverages[0] - 2 * standardDeviation;

  // Save the result as an object
  const bollingerBands = {
    "Upper bands": upperBand,
    "Middle Band": middleBand,
    "lower band": lowerBand,
  };

  return bollingerBands;
}

module.exports = {
  bb,
};
```

In this implementation:

The movingAverages array stores the calculated moving averages.

The standard deviation is calculated based on the moving averages.

The upper and lower bands are determined using the standard deviation.
