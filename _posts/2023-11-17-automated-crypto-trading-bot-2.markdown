---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_2
title: Automated crypto trading bot implementation 2 (with.Upbit Open API)
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

## This post is about "Implementing an automated cryptocurrency trading bot 2 (series)".

Nowadays, the value of cryptocurrencies is steadily increasing.

In a bull market, it is necessary to trade according to your own trading technique.

In this series, I'll show you how to create a trading bot that automatically executes trades based on the logic written in the code without you having to keep an eye on it.

In the previous post, we went through the preparation and project setup, so in this post, we'll actually start trading. (See: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

### How to use the Order API (Upbit Open API)

Upbit's Orders API is used to create orders for the markets you specify, and to retrieve orders. When creating an order, you need to specify the order side (side), order volume (volume), order price (price), and order type (ord_type).

### Configuring an Order API request

- URL: The endpoint for the Orders API is /v1/orders.
- Method: Use the POST method to create an order.

### Key parameters

- market (required): Specify the market ID of the cryptocurrency to trade. For example, "KRW-BTC" means a market that trades Bitcoin (BTC) in Korean Won (KRW).
- side (required): A parameter indicating the type of order.
- bid: Buy order (Buy)
- ask: A sell order (Sell)
- volume: Indicates the order volume. Required for buy orders.
- price: Indicates the order price. Required for limit orders (ord_type: limit) or market buy orders (ord_type: price).
- ord_type (required): Indicates the order type.
- limit: Limit order
- price: Market order (buy)
- market: Market order (sell)
- identifier: Optionally used as a custom value for lookup.

### Create a signature

To use the Orders API, you need an API key (access_key) and an API secret (secret_key).
You need to create a signature for security for API requests.
You create a signature by combining access_key, nonce, query_hash, and query_hash_alg.
The signature is generated in JSON Web Token (JWT) format and included in the Authorization header of the request.

### Example

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
Name Description Type
market * Market ID (required) String
side * Order type (required)
- bid : Buy
- ask : Sell String
volume * Order volume (required for limit, market sell) NumberString
price * Order price. (Required for limit, market buy)
ex) If you trade at 1,000 KRW per 1 BTC on the KRW-BTC market, the value will be 1000.
ex) In the KRW-BTC market, if the ask price is 500 KRW per 1 BTC, setting the value to 1000 when buying at the market will buy 2 BTC.
(This may vary depending on fees or the quantity of the first order) NumberString
ord_type * Order type (required)
- limit : Limit order
- price: Market order (buy)
- market : Market order (sell) String
Custom value for identifier lookup (optional) String (use Uniq value)
*/

const body = {
  market: "KRW-BTC",
  side: "bid",
  // volume: "0.01",
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

### Order execution function

In this code, we are defining a function, orderCryptocurrency, that utilizes the Upbit Open API to execute an order. This function performs the following functions

- Set the required parameters for the order.
- Generates a signature using the parameters.
- Set options for the API request.
- Performs the API request and returns the result.

### Example usage of this order execution function

```javascript
const { orderCryptocurrency } = require("./path/to/orderCryptocurrency");

// execute order
orderCryptocurrency()
  .then((result) => {
    console.log("Order result:", result);
  })
  .catch((error) => {
    console.error("Order failed:", error);
  });
```
