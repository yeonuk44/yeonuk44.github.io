---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Input_Data_Verification_And_Expression
title: About input data verification and expression
# title: About input data verification and expression
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
date: 2024-04-04 09:00:00 +0900
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

## This article discusses input data verification and expression.

hello! This time, we will learn about input data verification and expression during software development security.

Before starting the writing in earnest,

**---Today’s TMI---**

It's been a while since I played a game called 'League of Legends' with my friend.

It was fun, but I was also upset that they were ruining the game on purpose.

I finished the game without saying anything, and then pressed report for various reasons haha.

How do you deal with this situation? I wonder!

**---TMI End---**

Coming back, in this article we will also look at major security weaknesses: SQL injection, path manipulation, XSS, operating system command injection, dangerous format file upload, automatic connection to an untrusted URL address, and memory buffer overflow.

{:data-align="center"}

<!-- outline-end -->

### Overview of input data validation and representation

Input data verification is the process of checking the validity of data entered by the user.

Incorrect input data can lead to malicious attacks, so it is important to ensure that the data is trustworthy.

Additionally, the way the input data is represented also affects security, so the data must be represented in an appropriate manner.

### Major security weaknesses

- SQL Injection:
  SQL injection is when a malicious user attempts to attack a database by inserting SQL code into the input data. Input data should be validated, and interactions with the database should use parameterized queries or Object Relational Mapping (ORM) to prevent SQL injection.
- Path Traversal:
  Path manipulation is an attack where the user uses special characters such as "../" in the input data to manipulate paths in the file system. Path verification can prevent users from accessing inaccessible files.
- Cross-Site Scripting (XSS):
  XSS is an attack where a malicious user injects a malicious script into a web application and executes it in the user's browser. You must validate input data and use appropriate escaping techniques to prevent XSS attacks.
- OS Command Injection:
  Operating system command injection is an attack in which a malicious user takes control of a server's operating system by inserting malicious commands into input data. When validating input data and executing commands, it is safer to use APIs or libraries rather than executing system commands directly.
- Unsafe File Upload:
  A dangerous format file upload is when a malicious user attempts to attack a server by uploading a malicious file to a web application. You must ensure safe file upload by verifying the extension, size, and MIME type of the uploaded file.
- Automatic connection to an untrusted URL address:
  Automatic connection to an untrusted URL address is an attack that connects to a malicious site through a link that the user clicks. When creating links, make sure they are from trusted addresses and display a warning to users when using auto-connect connections to maintain a secure connection.
- Memory Buffer Overflow:
  A memory buffer overflow is an attack in which a malicious user manipulates the execution flow of a program by overflowing its memory through input data. You must verify the length of input data and use safe buffer management techniques to prevent memory buffer overflow.

## Conclusion

In this way, we learned about the importance of input data validation and representation, as well as major security weaknesses.

During software development, it is important to consider security and implement appropriate verification and defense mechanisms. thank you
