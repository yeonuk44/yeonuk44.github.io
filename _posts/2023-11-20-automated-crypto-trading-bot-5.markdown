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

## This post is about "Implementing an automated cryptocurrency trading bot 5 (series)".

Nowadays, the value of cryptocurrencies is steadily increasing.

In a bull market, it is necessary to trade according to your own trading technique.

In this series, we're going to create a trading bot that will automatically trade according to the logic written in the code without you having to keep an eye on it.

In the previous article, we learned what Bollinger Bands are and implemented this technical indicator directly in code. In this article, we will provide a step-by-step guide to the written code.

(Reference: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

### Install required modules

```javascript
npm install request
npm install uuid
npm install crypto
npm install jsonwebtoken
npm install querystring
npm install dotenv
```

### Set API key and secret

To use the Upbit Open API, get an API key and secret from the Upbit Developer Center and save it in an .env file.

```javasciprt
UPBIT_OPEN_API_ACCESS_KEY=your_access_key
UPBIT_OPEN_API_SECRET_KEY=your_secret_key
upbit_open_api_server_url=https://api.upbit.com
```

### Load required files and modules

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

### Implement the necessary functions

findKRW and findBTC: Functions to find the indices of KRW and BTC.

fetchData: Main function to collect data and execute the trading strategy

Please refer to the attached code repository in the outline of this article.

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

### Make periodic API calls and execute the trading strategy

```javascript
const minuteInterval = setInterval(async () => {
  // ...
}, 60000);
```

### Implementing a trading strategy

This example uses a simple trading strategy using Bollinger Bands.

```javascript
if (minuteCandlePrice <= lowerBand * 1.05) {
  // Buy order logic
} else if (minuteCandlePrice >= upperBand * 0.95) {
  // Sell order logic
}
```

If you've been following my series on automated cryptocurrency trading bots, you'll know which technical indicators I've utilized.

### Complementary and additional tasks

To extend this project, you can consider the following tasks

Optimize the strategy: The current strategy was implemented simply, but you can implement more complex strategies to maximize your profits.

### Finalizing

With these steps, you should be able to develop an automated trading bot while increasing your understanding of JavaScript and cryptocurrency trading.

If you have any gaps, feel free to contact us by email and we will get back to you.
