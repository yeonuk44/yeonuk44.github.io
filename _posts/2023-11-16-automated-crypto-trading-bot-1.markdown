---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Automated_Crypto_Trading_Bot_1
title: Automated crypto trading bot implementation 1 (with.Upbit Open API)
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
date: 2023-11-16 09:00:00 +0900
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

### This is an article about "Implementing an automated cryptocurrency trading bot (series)".

Nowadays, the value of cryptocurrencies is steadily increasing.

In a bull market, it is necessary to trade according to your own trading technique.

In this series, we're going to create a trading bot that will automatically trade based on the logic written in the code without you having to keep an eye on it.

{:data-align="center"}

<!-- outline-end -->

#### Preparation

- An Ubit account
- Your IP address (for security reasons, you will need a specific IP address to run the trading bot from)

#### Content

In order to use the information provided by any exchange, not just Ubit, you need to be aware of the existence of the Open API provided by that exchange.

Since we are using Javascript in this article, we will use npm, the project manager for Node.js.

1. First, go to the Open API section of the Help Center on the official Ubit website. (See: https://upbit.com/service_center/open_api_guide)
   After logging in and using the Open API, click Issue Open API Key to get an Open API key. At this point, check the scope of the technology you want to use in your trading bot.
   I checked all of them.
2. Create a project.
   Create a folder and install Node.js through the terminal.
   On Windows, you can download the installer from the official website (reference: https://nodejs.org/en), and on Mac, you can brew install node through Homebrew.
   Once Node.js is installed, use npm, Node's package manager, to set up the initial project.

```javascript
npm init -y // This is a quick way to set it up.
```

3. Install the library for using the OpenAPI.

```javascript
npm install request jsonwebtoken
```

4. Create an index.js file in your project and import the "Get full account" API usage example from the Uberbit Dev Center (see: https://docs.upbit.com/reference/%EC%A0%84%EC%B2%B4-%EA%B3%84%EC%A2%8C-%EC%A1%B0%ED%9A%8C)
   Imported code

```javascript
const access_key = process.env.UPBIT_OPEN_API_ACCESS_KEY;
const secret_key = process.env.UPBIT_OPEN_API_SECRET_KEY;
const server_url = process.env.UPBIT_OPEN_API_SERVER_URL;
```

#### Finalizing

As shown above, you need to enter the access_key, secret_key, and server_url as you received the Open API Key, respectively, but since I plan to share the project on GitHub, I added the dotenv library to the dependencies to manage the key as an .env file.

If you manage like me, you need to add a command to your gitignore file to exclude .env from changes. If you enter the key above and type $node index.js, it should run fine.
