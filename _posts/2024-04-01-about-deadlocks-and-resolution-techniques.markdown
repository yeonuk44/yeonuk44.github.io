---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Deadlocks_And_Resolution_Techniques
title: About deadlocks and resolution techniques
# title: About deadlocks and resolution techniques
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
date: 2024-04-01 09:00:00 +0900
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

## This article discusses deadlocks and resolution techniques.

hello! From today, I will add TMI that has nothing to do with the topic of the article little by little every day to bring life to the article.

**---Today’s TMI---**

Today is my 26th birthday.

Actually, I've done a lot of different things, but I was lost in thought for a while wondering if these experiences might be helpful in my life. For now, I plan to keep going with the thought that nothing will change if I don't do anything!

Do you also have any actions that you consistently do, regardless of their meaning? I don't know when it will happen, but I think it will help me in life!

We will support you!

**---TMI End---**

We'll come back and this time we'll look at deadlocks that can occur in computer systems and techniques for resolving them.

Deadlock refers to a situation where processes that are requesting and occupying system resources at the same time wait indefinitely for the resources they need.

This is an important concept because these situations can cause the system to stop working.

Let’s take a closer look now.

{:data-align="center"}

<!-- outline-end -->

### Necessary and sufficient conditions for deadlock to occur

- Mutual Exclusion: A resource must be available to only one process at the same time.
- Hold and Wait: A process must occupy at least one resource and wait for another resource.
- No Preemption: Resources already occupied by other processes cannot be forcibly taken away.
- Circular Wait: A circular structure formed to wait for resources must exist in a set of processes.

When these four conditions are met simultaneously, a deadlock can occur.

### Deadlock resolution techniques

- Deadlock Prevention: This is a method of preventing deadlock by removing one of the necessary and sufficient conditions for deadlock to occur. For example, you can eliminate ring waiting conditions by ensuring a consistent resource allocation order.
- Deadlock Avoidance: A method of preventing deadlock from occurring by checking the granting of resource requests in advance. A classic example is the banker algorithm, which allows resource allocation only to maintain a safe state.
- Deadlock Detection and Recovery: This is a method of detecting and recovering when a deadlock occurs. Deadlocks are detected through resource allocation graphs, etc., and the process involved in the deadlock is stopped or resources are preempted to recover.
- Deadlock Ignorance: If the possibility of a deadlock occurring is very low or if it does not significantly affect the system, the deadlock is ignored. In some real-time systems, it may make sense to ignore deadlock.

## Conclusion

Deadlock is a significant problem that threatens the stability of the system.

Therefore, system designers and developers must consider the possibility of deadlock occurring and select appropriate deadlock resolution techniques to maintain system stability.

This prevents potential problems caused by deadlock and ensures smooth system operation.
