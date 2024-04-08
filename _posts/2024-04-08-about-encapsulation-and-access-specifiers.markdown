---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Encapsulation_And_Access_Specifiers
title: About encapsulation and access specifiers
# title: About encapsulation and access specifiers
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
date: 2024-04-08 09:00:00 +0900
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

### Encapsulation

Encapsulation is one of the core concepts of object-oriented programming, which means grouping data and methods that process that data into a single unit.

This can enhance data confidentiality and security.

Encapsulation plays an important role when designing classes.

A class contains properties (data) and functionality (methods), and hiding these properties and functionality from the outside world is the core idea of encapsulation.

This allows you to access and manipulate data indirectly through methods without having to manipulate or change the data directly.

### Access specifier

Access specifiers are a tool for implementing encapsulation and are responsible for controlling access rights to members (properties and methods) of a class.

Major access specifiers include public, private, and protected.

- public: Any class can access this member.
- private: This member can only be accessed within the same class.
- protected: This member can be accessed within the same class, in the same package, and in subclasses in an inheritance relationship.

By using access specifiers to limit the scope of access to members, you can hide the internal implementation of a class from the outside world.

This ensures data confidentiality and prevents inappropriate access and modification from outside.

Additionally, access specifiers allow you to explicitly control access to and use of encapsulated members.

## Conclusion

Encapsulation and access specifiers are core concepts in object-oriented programming and are important tools for improving the readability and maintainability of code.

Encapsulation allows you to write safe and efficient programs by grouping data and functionality into a single unit and using access specifiers to clearly control the access scope of members.

Today we learned about encapsulation and access specifiers.

These concepts are important in object-oriented programming, and by understanding and utilizing them well, you can develop quality software.

thank you
