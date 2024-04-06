---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Inappropriate_Exception_Handing
title: About inappropriate exception handling
# title: Regarding inappropriate exception handling
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
date: 2024-04-06 09:00:00 +0900
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

## This article looks at inappropriate exception handling.

hello!

Today I would like to talk about inappropriate exception handling in software development.

Before starting the writing in earnest,

**---Today’s TMI---**

Tonight’s dinner is ‘sukju chadol stew’! Since I'm planning to cook it at home, I'm very nervous and I want to eat it quickly. Haha, I've made a dish called 'sul-steamed' before, putting cabbage on the bottom, putting pork on it, pouring soju over it, and steaming it. It's so simple and doesn't require much work, and it's so delicious! I think you should try it too!

**---TMI End---**

Coming back, exception handling, which appears in this article, is an important concept that handles errors in preparation for unexpected situations that may occur during program execution.

However, developers often implement exception handling improperly.

Now, let’s take a closer look.

{:data-align="center"}

<!-- outline-end -->

### Improper exception handling

The most common example of improper exception handling is ignoring exceptions.

If developers ignore exceptions and move on, they end up putting the problem on hold without taking appropriate action to respond to the exception.

This can reduce program stability and make it difficult to identify and resolve the cause of exception situations.

Additionally, using exception handling that is too broad is also problematic.

Instead of handling all exceptions at once, it is important to be specific and clear about exception handling.

Exception handling that is too extensive makes it difficult to pinpoint errors and makes debugging difficult.

Moreover, it may create security vulnerabilities.

Finally, providing inappropriate exception messages is also a problem.

Clear and useful exception messages are an important tool to aid debugging and error resolution.

However, if developers provide inappropriate messages or do not clearly explain the cause of the exception and how to handle it, it becomes difficult for other developers or maintainers to identify the problem.

Such inappropriate exception handling can reduce software stability and maintainability.

So, let's look at some ways to properly handle exceptions.

### How to properly handle exceptions

1. Do not ignore exceptions, but handle them appropriately. By handling exceptions appropriately, you can improve the stability of your program.
2. Specific and clear exception handling must be applied. You must write an appropriate handling method for each exception, and document the cause and action method of the exception to make it easy for other developers to understand.
3. Provide clear and useful exception messages. Exception messages should contain important information to help you identify and resolve the error. Therefore, developers must write exception messages carefully.

## Conclusion

Exception handling is an essential element in software development.

Improper exception handling can reduce the stability and maintainability of software, so it is important to follow the principles for correct exception handling.

thank you
