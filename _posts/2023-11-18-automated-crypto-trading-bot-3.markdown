---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_3
title: Automated crypto trading bot implementation 3 (with.Upbit Open API)
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

## This post is about "Implementing an automated cryptocurrency trading bot 3 (series)".

Nowadays, the value of cryptocurrencies is steadily increasing.

In a bull market, it is necessary to trade according to your own trading technique.

In this series, I'm going to create a trading bot that automatically executes trades based on the logic written in the code without me having to keep an eye on it.

In the previous article, we performed the trades manually, so in this article, we'll be fetching candle information and getting values to implement investment techniques such as Bollinger Bands.(Reference: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

### Get Candlestick Information API

Upbit's Candlestick Data API allows you to get candlestick data for a specific market. This can be used for trend analysis, technical analysis, and many other purposes.

My code

getDailyCandlesInfo function

```javascript
function getDailyCandlesInfo() {
  // Set the API request options
  const options = {
    method: "GET",
    url: "https://api.upbit.com/v1/candles/days?count=30&market=KRW-BTC",
    headers: { accept: "application/json" },
  };

  // Process the API request and response
  return new Promise((resolve, reject) => {
    request(options, (error, response, body) => {
      if (error) {
        reject(error);
      } else {
        try {
          // Parse the JSON
          const responseBody = JSON.parse(body);

          // Extract only the candle's trade prices
          const tradePrices = responseBody.map((candle) => candle.trade_price);

          // Calculate the value using technical analysis (Bollinger Bands)
          const dailyBBValue = technicalBollingerBand.bb(tradePrices);

          // return the result
          resolve(dailyBBValue);
        } catch (parseError) {
          reject(parseError);
        }
      }
    });
  });
}
```

The above code requests and receives the daily candle information of the KRW-BTC market through QS, parses it into JSON format, and extracts only the closing price of the desired candle.

We inserted it into the Bollinger Bands function that will be used in the next article to calculate the technical analysis basis for the trade.

Here is the code to get the candle information per minute for trading.

getMinuteCandleInfo function

```javascript
function getMinuteCandleInfo() {
  // Set the API request options
  const options = {
    method: "GET",
    url: "https://api.upbit.com/v1/candles/minutes/1?market=KRW-BTC&count=1",
    headers: { accept: "application/json" },
  };

  // Process the API request and response
  return new Promise((resolve, reject) => {
    request(options, (error, response, body) => {
      if (error) {
        reject(error);
      } else {
        try {
          // Parse the JSON
          const responseBody = JSON.parse(body);

          // Extract only the candle's trade prices
          const tradePrices = responseBody.map((candle) => candle.trade_price);

          // return the result
          resolve(tradePrices);
        } catch (parseError) {
          reject(parseError);
        }
      }
    });
  });
}
```

We've also imported an example that uses the code written above.

Example of using

```javascript
const { getDailyCandlesInfo, getMinuteCandleInfo } = require("./path/to/api");

// Get daily candle information
getDailyCandlesInfo()
  .then((dailyBBValue) => {
    console.log("Daily Bollinger Bands value:", dailyBBValue);
  })
  .catch((error) => {
    console.error("Failed to retrieve daily candle information:", error);
  });

// Get minute candle information
getMinuteCandleInfo()
  .then((tradePrices) => {
    console.log("Minute candle trade prices:", tradePrices);
  })
  .catch((error) => {
    console.error("Failed to retrieve 1-minute candle information:", error);
  });
```

### Wrapping up

Utilizing Upbit's candlestick data retrieval API can help you identify market trends and perform technical analysis.

You can use the functions above to get candlestick information, analyze it as needed, and use it to make investment decisions.

In the next article, we will look at implementing technical analysis indicators such as Bollinger Bands through algorithms, and furthermore, implementing a trading bot that applies investment techniques through periodic API calls.

Thanks for reading.
