---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Log_Analysis
title: About log analysis
# title: About log analysis
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
date: 2024-04-15 09:00:00 +0900
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

## This is an article about log analysis.

hello!

This time, we will learn about log analysis.

Before starting the writing in earnest,

**---Today’s TMI---**

It's been a while since I played a proper game called Lost Ark, and the raid was really fun!

There seems to be a lot of inflow, so I'm looking forward to the next new user event.

If you are interested in the RPG genre, give it a try!

**---TMI End---**

Let’s get back to writing!

Logs are important tools for recording information related to the behavior of a system.

In particular, kernel logs refer to logs created by the kernel, which is a core part of the system.

In this article, we will learn about the most commonly used kernel logs: wtmp, utmp, btmp, and lastlog.

{:data-align="center"}

<!-- outline-end -->

### wtmp log

The wtmp log contains information about users logging into the system and logging out.

These logs are used to track and analyze user activity by recording login-related information.

It is primarily utilized for security auditing and user activity tracking purposes.

For example, wtmp logs include a user's login history, logout history, session start and end times, etc.

### utmp log

The utmp log records information about the currently logged in user.

Similar to wtmp logs, but utmp logs only contain information about the current session.

This log is used by system administrators to monitor current user activity in real time and identify sessions that do not log out.

For example, the user's login time, terminal device, process ID, etc. are included in the utmp log.

### btmp log

The btmp log records information about login attempts.

Even if a login attempt fails, the information is recorded and used to analyze and track security issues.

For example, the ID of the user who attempted to log in, the time of the failed login, the failed IP address, etc. are included in the btmp log.

### lastlog log

The lastlog log records information related to the last time a user logged in.

These logs are used to track users' login history and identify users who have not logged in for a long time.

For example, the lastlog log includes the user's last login time, login terminal device, and IP address.

## Conclusion

These kernel logs provide important information for system security and auditing.

Through log analysis, you can identify abnormal system behavior, security threats, user activities, etc.

This is a useful resource to help investigate security-related issues or solve system problems.
