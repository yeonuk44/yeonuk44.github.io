---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Data_Formats_In_APIs
title: About understanding data formats in APIs
# title: About understanding data formats in APIs
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Network
# multiple tag entries are possible
tags: [network]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-30 09:00:00 +0900
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

## outline

Application programming interfaces (APIs) are a key element for seamlessly exchanging data between software applications.

Understanding data formats is very important when working with APIs.

In this article, we'll look at the differences between strings commonly used in API interactions and JavaScript Object Notation (JSON).

<!-- outline-end -->

### String: Basic text data

A string represents text data as a sequence of characters.

It is one of the fundamental data types in most programming languages.

APIs often transmit data over a network in string format.

This is because the network works more efficiently with text data.

### JSON: Lightweight data exchange

JSON, on the other hand, is a lightweight data exchange format.

It can be easily read and written by both people and machines.

JSON provides a structured way to represent data objects as attribute-value pairs and is well suited for data exchange.

#### Why use strings in API responses?

When an API responds to a request, it usually returns data in string format.

This is due to the nature of network communication.

Strings are more efficient to transmit over networks and provide a universal format for reading data.

### JSON parsing: Convert string to object

When you receive an API response in string format, you typically need to convert it into a format usable by your programming language.

In JavaScript, you use the JSON.parse() function to convert a JSON string to a JavaScript object or array.

This parsing step allows you to utilize your data effectively.

#### Real-life example

Let's consider an API that returns financial market data.

There may be cases where it returns daily candlestick information for a cryptocurrency such as Bitcoin (BTC).

The response will be a JSON string containing details such as open price, close price, high price, low price, volume and timestamp for multiple dates.

```javascript
const apiResponse =
  '[{"market":"KRW-BTC","candle_date_time_utc":"2023-11-15T00:00:00", ... }]';

const parsedData = JSON.parse(apiResponse);
console.log(parsedData);
```

In the example above, parsedData now holds the API response as a JavaScript object, allowing developers to easily access specific data fields such as trade_price.

### conclusion

Understanding the interaction between strings and JSON in API interactions is essential for effective data exchange and utilization.

If you're developing an application that uses an API or designing an API, being aware of the role these data types play will help you work seamlessly within the broader software ecosystem.
