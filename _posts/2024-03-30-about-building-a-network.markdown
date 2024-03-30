---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Building_A_Network
title: About building a network
# title: About building a network
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
date: 2024-03-30 09:00:00 +0900
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

## This is an article about network construction.

Today we will learn about building a network.

A network is a system where computers and other devices are connected to each other and can exchange information.

When building a network, you need to know about various installation structures, classifications, standards, and communication technologies.

Now let’s look at them one by one.

{:data-align="center"}

<!-- outline-end -->

### Network installation structure:

- Forming: Computers are connected in a circle, with one computer directly connected to another.
- Ring type: Computers are connected in a ring shape, and each computer is directly connected to the computer on either side.
- Bus type: Computers are connected in a row, and all computers share the same communication medium.
- Hierarchical: Multiple small networks are organized hierarchically, with upper layers using routers to communicate with lower layers.
- Network type: A form in which multiple computers are complexly connected, allowing communication through multiple paths.

### Network classification:

- LAN (Local Area Network): A network used in a small geographical area, and is used in limited spaces such as indoors or inside buildings.
- WAN (Wide Area Network): A network that covers a wide geographical area and is used in large-scale networks such as the Internet.

### LAN standard (IEEE 802.x):

LANs follow standardized specifications from the Institute of Electrical and Electronics Engineers (IEEE).

In particular, the LAN standard is known as the IEEE 802.x series.

x stands for various versions, each version defining specifications for a particular technology or communication method.

### Versions of 802.11:

802.11 is part of the IEEE 802.x series that defines standards for wireless local area networks (WLANs).

802.11 was initially a wireless communication technology that provided speeds of 2Mbps, but it gradually evolved and various versions emerged.

For example, there are 802.11b, 802.11g, 802.11n, and 802.11ac, and each version may have different speeds and compatibility.

### CSMA/CD and CSMA/CA:

CSMA/CD (Carrier Sense Multiple Access with Collision Detection) is a method of detecting and handling collisions in wired networks such as Ethernet.

If a conflict occurs, it waits for a certain amount of time and then attempts to retransmit.

CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance) is a method to prevent collisions in wireless networks.

Before transferring data, it checks to see if other devices are in use and throttles transfers to minimize conflicts.

## Conclusion

Above, I have written a blog-style article about network construction.

We briefly looked at network installation structure and classification, LAN standards, and wireless communication technology.
