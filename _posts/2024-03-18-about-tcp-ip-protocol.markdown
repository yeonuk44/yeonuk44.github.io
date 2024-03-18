---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_TCP_IP_Protocol
title: About TCP/IP protocol
# title: About TCP/IP protocol
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
date: 2024-03-18 09:00:00 +0900
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

## This is an article about the TCP/IP protocol.

In this article, we are preparing an information processing article, and this time we will learn about the TCP/IP protocol.

TCP/IP is the most widely used set of protocols in Internet communications and is an important concept that underlies network communications.

Let’s take a look at it together.

{:data-align="center"}

<!-- outline-end -->

### What is TCP/IP protocol?

TCP/IP stands for Transmission Control Protocol/Internet Protocol, and is a set of protocols for communication between computers on the Internet.

This protocol provides stable and reliable communication by performing various functions such as data transmission, route establishment, and error detection and recovery.

### Main components of TCP/IP protocol

**Internet Protocol (IP, Internet Protocol)**

IP is the main protocol used to send and receive data on the Internet.

The data is divided into packets, the destination is identified and transmitted.

IP addresses identify computers and perform routing.

**Transmission Control Protocol (TCP)**

TCP is a protocol responsible for data reliability and flow control.

Divides data into segments, performs error recovery and retransmission.

It has connection-oriented characteristics and ensures reliable data transmission.

### Internet Control Message Protocol (ICMP)

ICMP is a protocol that transmits error messages over a network and monitors network status.

Used for detecting network conditions and resolving errors.

### Domain Name System (DNS)

DNS is a system that performs translation between IP addresses and domain names.

It is used for communication by converting human-understandable domain names into IP addresses.

### File Transfer Protocol (FTP)

FTP is a file transfer protocol that supports file transfer between clients and servers.

Provides functions such as file upload, download, and deletion.

**Email Protocol (SMTP, Simple Mail Transfer Protocol)**

SMTP is a protocol for sending and receiving email.

It is used for sending and receiving emails and supports communication between different mail servers.

### Advantages of TCP/IP protocol

Ensures interoperability between various systems and devices on the network.

Provides stable and reliable communication in large-scale networks such as the Internet.

By supporting a variety of application protocols, we can provide a variety of services.

It is an open standard and has high compatibility with other protocols.

## Conclusion

The TCP/IP protocol is the most basic protocol in various network environments, including the Internet, and is essential for understanding and configuring network communications.

Understand the role and function of each protocol and use it to solve problems related to network configuration.
