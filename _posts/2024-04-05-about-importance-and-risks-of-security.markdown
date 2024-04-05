---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Importance_And_Risks_Of_Security
title: About the importance and risks of security
# title: About the importance and risks of security
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-04-05 09:00:00 +0900
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

## This article explores the importance and risks of security.

hello!

Before starting the writing in earnest,

**---Today’s TMI---**

I had a hamburger and milkshake today at a burger place called ‘Frank Burger’ and it was so delicious! Personally, it's the #1 burger haha. If you get a chance, be sure to try it!

**---TMI End---**

Coming back, in this article I'd like to talk about the importance of security and the dangers of hardcoded passwords.

{:data-align="center"}

<!-- outline-end -->

### outline

Many web applications and software use encryption to secure passwords when they are stored or transmitted.

However, some developers still hardcode passwords into their source code for convenience.

However, hardcoded passwords can pose a huge security risk.

If the code is made public or exposed to a malicious attacker, your password can easily be stolen.

This may lead to users' personal information being leaked and system breaches.

### How to replace hardcoded passwords

1. Using environment variables. Environment variables are settings provided by the operating system or application and are a secure place to store encrypted passwords. This allows you to use it without having to write the password directly in your source code.
2. Utilize external storage. The encrypted password is stored in external storage, and the application accesses the storage to use the password. This will increase the security of your password.
3. It is also a good idea to get help from a security expert. Security experts are familiar with the latest security technologies and principles and can suggest appropriate security solutions. Therefore, it is very important to get professional advice on security.

To develop and use more secure applications, you should avoid using hardcoded passwords.

Instead, encrypted passwords should be stored securely and appropriate security measures should be adopted to protect users' personal information.

## Conclusion

It is everyone's responsibility to recognize the importance of security and take appropriate measures to manage passwords.

We must continue to do our best to develop and use with security in mind. thank you
