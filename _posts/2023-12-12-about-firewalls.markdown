---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Firewalls
title: About firewalls
# title: About firewalls
# post specific
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
date: 2023-12-12 09:00:00 +0900
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

## This article is about the "About Firewalls" issue.

This article summarizes the concepts I learned while studying networking.

{:data-align="center"}

<!-- outline-end -->

### Concepts

A firewall is a device or software used to monitor and control network traffic on a computer network to maintain security.

Firewalls serve to protect networks and computer systems from illegal access, hacking, viruses, spyware, and other malicious activity.

### Roles

1. Packet filtering: A firewall examines data packets (small pieces of data sent across a network) to determine which way the received data should be allowed or blocked based on the rules of what is allowed. These rules are related to port numbers, IP addresses, protocols, etc.
2. Stateful tracking: Some firewalls track the state of network connections to ensure that data packets are from allowed connections. This is used to further enhance security.
3. Application layer inspection: Advanced firewalls can analyze the contents of data packets to detect and block the behavior of specific applications.
4. Malware and spyware blocking: Firewalls can detect and block viruses, worms, Trojans, spyware, and other malicious code.
5. Virtual private network (VPN) support: Some firewalls support VPN connections for secure remote access.
6. Security logging and monitoring: Firewalls record network activity in logs and allow security administrators to monitor what is happening on the network.

There are some attacks that firewalls can't stop. Let's learn more.

#### How firewalls don't stop attacks

Firewalls primarily filter and allow or block traffic by examining the packet headers of network traffic (the packet's origin, destination IP address, port number, etc.).

However, firewalls typically do not deeply analyze the content of the communication data itself.

Because of this, they may not be able to stop attacks in the following cases.

#### Types of attacks they won't stop

1. Encrypted traffic: Firewalls let encrypted traffic (such as HTTPS) through because they don't understand the content of the traffic. The data inside the encrypted traffic is not decrypted by the firewall, and an attacker can hide malicious activity through encrypted communication.
2. Zero-Day Attacks: Firewalls use known attack signatures to inspect traffic, but in the case of a new or zero-day attack, the firewall may not detect it. This is when an attacker exploits a previously unknown vulnerability.
3. Confusion with legitimate data: Firewalls attempt to detect malicious behavior by examining patterns in traffic, but sometimes it is difficult to distinguish between legitimate and malicious data. For example, malicious code may be hidden as part of a data file.
4. Human social engineering: Firewalls have difficulty monitoring people's communications or detecting social engineering attacks (attacks that trick users). These attacks rely primarily on human interaction and are difficult for firewalls to prevent.
5. Complex malware: Firewalls can be effective at detecting simple malware, but advanced malware can bypass or evade firewalls.

### Conclusion

Firewalls play an important role in securing your network, but they don't provide complete security.

Therefore, it is common to use them in conjunction with other security solutions to protect your network and systems.
