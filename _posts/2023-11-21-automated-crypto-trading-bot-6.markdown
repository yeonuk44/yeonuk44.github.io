---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_6
title: Automated crypto trading bot implementation 6 (with.Upbit Open API)
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

## This post is about "Implementing an automated cryptocurrency trading bot 6 (series)".

Nowadays, the value of cryptocurrencies is steadily increasing.

In a bull market, it is necessary to trade according to your own trading technique.

In this series, we will create a trading bot that automatically trades according to the logic written in the code without me having to look at it.

In the previous article, I provided a step-by-step guide to the code that was written.

In this article, we'll go all the way to querying the market and exporting the resulting values to a JSON file to trade more cryptocurrencies.

(See: https://github.com/yeonuk44/Trading-Bot)

{:data-align="center"}

<!-- outline-end -->

### Get market code

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

That's all it takes to get it to load.

However, I want to use modularity so that it's only used when needed, so I'm going to create a new market.js and make that function exportable.

### Get my market.js code

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

This will ensure that when that function is called, it will output the results in the form of json as declared in the responseBody.

Furthermore, I want to generate a file with the json and export the results, so let's modify the code accordingly.

### JSON file generation code

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

          // Create a JSON file
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

### Wrapping up

The fs module in Node.js makes it simple to manipulate the file system. In addition to creating JSON files, you can also read, update, delete, and more, so use it for whatever functionality you need.

That's it for this simple example of working with the file system in Node.js. We hope you found it useful.
