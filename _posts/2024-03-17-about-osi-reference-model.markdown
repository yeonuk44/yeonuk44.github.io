---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_OSI_Reference_Model
title: About the OSI Reference Model
# title: About the OSI Reference Model
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
date: 2024-03-17 09:00:00 +0900
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

## This is an article about the OSI reference model.

In this article, we are preparing an information processing article, and this time we will learn about the OSI (Open Systems Interconnection) reference model.

This model for understanding the structure of network communications is widely used around the world.

Let’s take a look at it together.

{:data-align="center"}

<!-- outline-end -->

### Layers of the OSI Reference Model

**Physical Layer**

Transmits data as electrical signals or bit streams.

It covers the physical connections and transmission media required for data transmission.

**Data Link Layer**

Divide data into blocks and perform error detection and correction.

Data transmitted from the physical layer is organized in the form of a frame.

### Network Layer

Select the most efficient path among multiple paths and transmit the packet.

The destination is identified through the IP address and routing is performed.

**Transport Layer**

Responsible for data reliability and flow control.

Divides data into segments, performs error recovery and retransmission.

### Session Layer

It is responsible for establishing, maintaining, and terminating communication sessions.

Responsible for data synchronization and conversation control.

**Presentation Layer**

Performs conversion tasks such as format conversion, encryption, and compression of data.

Convert data into a format that the application layer can understand.

### Application Layer

Provides an interface between users and the network.

It provides services to user applications and is the final destination for data.

**Advantages of the OSI Reference Model**

The layered structure makes it easy to understand each step of network communication.

Ensures compatibility between different vendors or protocols.

You can predict how changes in one layer will affect other layers.

As a standardized model, it is useful for network design and problem solving.

## Conclusion

The OSI reference model is an important tool for understanding the fundamental concepts of network communications.

Understand the roles and functions of each layer and approach network configuration and problem solving based on this.
