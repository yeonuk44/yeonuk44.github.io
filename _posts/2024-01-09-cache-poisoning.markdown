---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Cache_Poisoning
title: 캐시 독점에 대하여
# title: About Cache Poisoning
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: DNS
# multiple tag entries are possible
tags: [dns, cache]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-09 09:00:00 +0900
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

## About "Cache Poisoning"

As you learn about DNS, you'll also learn about web caching, which we covered in a recent post.

{:data-align="center"}

<!-- outline-end -->

### What is cache poisoning?

An attack in which an attacker injects false information into the cache of a Domain Name Systm (DNS) server, manipulating it to return an invalid IP address.

What happens if an invalid IP address is returned?

The attacker can try to manipulate the victim's DNS requests and redirect them to a malicious website or launch a variety of other attacks, including man-in-the-middle attacks.

### What is a man-in-the-middle attack?

A form of attack in which a third party intervenes in the middle of the path to eavesdrop, manipulate, or forge communications.

This attack means that the two sides sending and receiving the communication trust each other, and the attacker steps in between to steal or manipulate the information.

Coming back to cache poisoning, it is also called a host head attack, but what is a host head?

### What is a host head?

It is one of the headers used in an HTTP request, which conveys the domain name that the client is requesting from the server.

This attack manipulates the host header to trick the server into responding, causing it to cache the incorrect response, which will affect other clients as well.

### Conclusion

Cache monopolization is a security risk, and proper defense and protection measures must be taken on DNS servers and web servers.

To do this, you should consider cache invalidation, cache control policies, and proper DNS security settings.
