---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Route_And_Traffic_Control
title: About route and traffic control
# title: About route and traffic control
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
date: 2024-03-31 09:00:00 +0900
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

## This is an article about routes and traffic control.

In networks, there are important concepts called path control and traffic control.

They play an essential role in maintaining the efficiency and stability of the network.

In this article, we will look at an overview of path control, path control protocol, traffic control, flow control, congestion control, and deadlock prevention.

{:data-align="center"}

<!-- outline-end -->

### Overview of route control

Path control is the process of determining which path a packet should follow as it passes through a network.

This ensures that packets are sent to their destination via the optimal path, improving network efficiency and performance.

Route control uses routing protocols to exchange route information and determines the optimal route through a route selection algorithm.

### Path Control Protocol

Path control protocol is a protocol for exchanging path information between network devices.

Representative path control protocols used include OSPF (Open Shortest Path First), BGP (Border Gateway Protocol), and RIP (Routing Information Protocol).

These protocols perform path control in various situations according to their respective characteristics and purposes.

### Traffic Control

Traffic control is a technology that controls the flow of data that occurs in a network.

A variety of traffic can occur simultaneously on a network, and efficient traffic control is important to maintain network performance and stability.

Traffic control includes prioritizing traffic, allocating bandwidth, and controlling congestion.

### Flow control

Flow control is a technology for regulating the data transmission rate between the transmitting and receiving sides.

The data transmitting side transmits data according to the processing speed of the receiving side to prevent congestion, and the receiving side informs the sending side of the time to process the data to prevent excessive data transmission.

This helps improve network efficiency and prevent data loss.

### Congestion control

Congestion control is a technology that prevents network resources from being overloaded due to excessive requests to the network.

To this end, methods such as traffic monitoring, traffic filtering, and limited bandwidth allocation are used to promote efficient use of network resources.

### Deadlock prevention

Deadlock is a condition that can occur in a network, where each device waits infinitely for each other's resources.

Deadlocks can degrade network performance and cause the entire system to stop functioning.

To prevent this, we use deadlock detection and recovery algorithms to solve the problem and appropriately adjust resource allocation and release.

## Conclusion

Path control and traffic control are key concepts for network efficiency and stability.

Path control determines the optimal path to ensure efficient delivery of packets, and traffic control improves network performance by regulating data flow.

In addition, it supports efficient use of data transmission and network resources through flow control and congestion control, and maintains network stability by preventing deadlock.

It is important to utilize these concepts appropriately to optimize network operations.
