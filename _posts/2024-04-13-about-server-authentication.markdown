---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Server_Authentication
title: About server authentication
# title: About server authentication
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
date: 2024-04-13 09:00:00 +0900
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

## This is an article about server authentication.

hello!

For those who want to learn about server authentication, this time we will learn about authentication, authorization, knowledge, possession, and behavior-based authentication.

Before starting the writing in earnest,

**---Today’s TMI---**

I received certification in word processing and computer literacy!

I looked at the questions without any self-study books or online lectures, and continued to solve past exam questions, but I did well on both the written and practical exams, so I passed!

Today has been a good day haha I hope you all have a good day too!

**---TMI End---**

Let’s get back to writing!

Server authentication is a very important concept in information security and is important to understand.

{:data-align="center"}

<!-- outline-end -->

### Authentication

Authentication is the process by which a user proves who they are.

Users trying to access a server often provide a username and password to prove their identity.

This information allows the server to verify who the user is and complete authentication.

### Authorization

Authorization is the process of granting an authenticated user permission to access a specific resource or service.

For example, authorization determines whether an authenticated user can access a particular directory or modify a file.

### Knowledge-based Authentication

Knowledge-based authentication is where users verify their identity by providing accurate answers to predefined questions.

For example, you must provide accurate answers to questions such as “Where were you as a child?” to complete the verification.

### Possession-based Authentication

Possession-based authentication uses a physical device or media owned by the user to authenticate.

A representative example is entering a one-time authentication number sent via SMS.

This method completes authentication by verifying that the user owns the phone.

### Behavior-based Authentication

Behavior-based authentication is a method of verifying a user's identity by analyzing specific behavioral patterns.

Authentication is performed by analyzing the user's typing style, mouse usage patterns, touch movements, etc.

This method is considered highly secure because it is based on the user's characteristic behavior.

Server authentication can also be done by combining the various methods introduced above.

For example, after authenticating with an ID and password, a user can use the method of entering a one-time authentication number sent via SMS as an additional authentication step.

## Conclusion

This is a brief introduction to the concept of server authentication.

To help you understand, we have included various authentication methods in the explanation. For more secure server authentication, it is recommended to use multiple authentication methods.

Each authentication method has its pros and cons, so it is important to use an appropriate combination to suit the situation.

thank you
