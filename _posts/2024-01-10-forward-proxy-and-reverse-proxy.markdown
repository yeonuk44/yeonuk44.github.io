---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Forward_Proxy_And_Reverse_Proxy
title: About Forward proxy and Reverse proxy
# title: About Forward proxy and Reverse proxy
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
date: 2024-01-10 09:00:00 +0900
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

## About "forward proxy and reverse proxy"

This is a summary of concepts I learned while studying networks.

Computer network and web security play a key role in modern business and personal activities.

In these areas, forward proxies and reverse proxies are important security tools.

In this article, we'll take a look at what forward and reverse proxies are and how they contribute to securing network communications.

Before we discuss forward and reverse proxies, let's first understand what a proxy is.

{:data-align="center"}

<!-- outline-end -->

### What is a proxy?

The general concept of a server or software that acts as an intermediary in network communication.

A proxy sits between a client and a server, receiving requests from the client, forwarding them to the server, and returning responses from the server to the client.

With this intermediary role, proxies are used for a variety of purposes.

Let's take a look at forward and reverse proxies.

### The concept of a Forward Proxy

A forward proxy is a server that acts as a relay between a client and an external server.

Instead of the client connecting directly to the external server, it connects through the forward proxy.

This relay role is used for a variety of purposes.

#### Purpose

- Increase security: A forward proxy provides anonymity by hiding the client's real IP address and instead exposing the IP address of the proxy server. This helps protect the client's privacy and location information.
- Caching: A forward proxy saves copies of previously requested data and serves the stored data instead of the client when the same request occurs again, saving bandwidth and speeding up response times.
- Access control: It can be used to manage web usage within an organization and control access to specific websites.

### Concept of Reverse Proxy

A reverse proxy is a server that acts as a relay for external requests to an internal server.

The client communicates with the internal server through the reverse proxy, and the internal server does not communicate directly with the client.

This architecture is used for the following purposes

#### Purpose

- Increase security: The reverse proxy hides the location of the internal server and controls the communication between the client and the external server. This is used to filter and validate external requests without directly exposing the internal server.
- Load balancing: A reverse proxy balances the load by distributing requests to multiple internal servers. This can improve the performance of your system and maintain availability.
- SSL encryption: A reverse proxy decrypts SSL/TLS encryption and enables secure communication with internal servers.
- Caching: A reverse proxy caches responses to external requests to provide faster responses to the same request.

### Conclusion

You can decide where to place your proxy based on the role and purpose of your project.
