---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Transparent_Proxy
title: About transparent proxy
# title: About transparent proxy
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
date: 2024-01-20 09:00:00 +0900
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

## About "Transparent Proxy"

I previously wrote an article titled "Forward and reverse proxies play an important role in network security".

In this article, I'll be documenting what I've learned about proxies as a continuation of that topic.

{:data-align="center"}

<!-- outline-end -->

### Introduction

When sending and receiving data on the internet, information travels through various paths.

One of these paths is through a "proxy".

Proxies relay communication between clients and servers and are used for a variety of purposes, including security, performance optimization, and caching.

A "transparent proxy" is a special type of proxy server that works as transparently as its name suggests, and in this article, we'll learn more about it.

#### What is a transparent proxy?

A transparent proxy is an intermediary that relays communication between a client and a server, characterized by the fact that the client and server use each other as proxy servers.

This means that the existence of the proxy server is hidden from the user or application, and network traffic is relayed transparently.

A transparent proxy is invisible to users or applications, and does not change the content of network traffic while mediating it.

#### How it works

One of the key characteristics of a transparent proxy is "transparency".

This means that the user or application is unaware of the existence of the proxy server.

The proxy server operates in the middle, without any user awareness in the network equipment or application settings.

A transparent proxy sits in the middle when a client accesses a server, receiving the client's request and forwarding it to the server.

It also receives responses from the server and forwards them to the client.

In the process, the proxy acts as an intermediary between the client and server, and can monitor traffic or perform caching, security checks, logging, and more if needed.

#### Utilizing a transparent proxy

Transparent proxies serve a variety of purposes.

Let's take a look at some of them.

- Caching: A transparent proxy can cache the responses it receives from the server so that it can respond quickly to the same request in the future. This helps optimize performance.
- Security inspection: Proxies can inspect network traffic to detect and block malicious code or hacking attempts.
- Logging and surveillance: Proxies can monitor network activity and record logs, which can be used for security and error diagnostics.

#### Conclusion

A transparent proxy relays network communications while remaining transparent to the user or application.

In the meantime, they monitor network traffic and serve a variety of purposes, including security, performance optimization, and caching.

These transparent relay servers play a key role in network management and security.
