---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Recovery_And_Parallel_Control
title: About recovery and parallel control
# title: About recovery and parallel control
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: DB
# multiple tag entries are possible
tags: [db]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-04-02 09:00:00 +0900
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

## This is an article about recovery and parallel control.

hello!

**---Today’s TMI---**

It's been a while since I called my father to say hello. It was your time at work, but I suddenly wanted to hear your voice and called you. The truth is... he hadn't considered it at all. The time zone I live in and the time zone office workers live in are different. From now on, we will have to consider more detailed details. Nevertheless, I love you, Dad, for accepting me so well!

**---TMI End---**

We'll come back and this time we'll look at recovery and concurrent control, which are important concepts in databases.

These two techniques used to maintain data consistency in a database are important and essential concepts.

Let’s take a closer look now.

{:data-align="center"}

<!-- outline-end -->

### Recovery

Recovery refers to the process of recovering from a system failure or error in a database.

System failures can compromise the consistency and integrity of data.
Recovery techniques refer to the process of restoring such corrupted data to its original, consistent state.

### Immediate Update Technique

The immediate update technique refers to a method where when data is updated in the database, the update operation is immediately reflected on the disk.

This ensures data consistency and minimizes recovery efforts in the event of a system failure.

### Concurrency Control

Concurrency control is a technique to ensure data consistency in situations where multiple users access and update the database at the same time.

During parallel processing, update operations may overlap as multiple transactions are executed simultaneously.

In these situations, concurrency control techniques control and coordinate the execution of transactions to maintain data consistency.

### Locking

Locking is one of the main techniques used in parallel control.

Locking means setting a lock on data when a transaction accesses it.

While one transaction is updating data, it prevents other transactions from accessing that data.

This helps maintain data consistency and prevent update conflicts.

### Timestamp Ordering

Timestamp ordering is a technique used to determine the execution order of transactions.

Each transaction is given a unique timestamp, and the execution order of transactions is determined based on this.

This helps prevent conflicting update operations and maintains data consistency.

### Locking Granularity

Locking unit refers to the unit that applies locking.

The locking unit is determined by the size of the database and the nature of the transactions.

For example, low-level locking means locking individual data records, while table-level locking means locking the entire table.

## Conclusion

Recovery and concurrency control are important elements for maintaining data consistency and integrity in database systems.

Implementing this effectively can increase the stability and reliability of your database system.

Therefore, developers can operate database systems more stably through understanding and appropriate application of recovery and parallel control.
