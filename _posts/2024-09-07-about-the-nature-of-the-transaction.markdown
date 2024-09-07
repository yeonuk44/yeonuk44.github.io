---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Nature_Of_the_Transaction
title: About the nature of the transaction
# title: About the nature of the transaction
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
date: 2024-09-07 09:00:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_comm  on_description in _data/owner/[language].yml
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

## This article examines the characteristics of transactions.

Hello!

A transaction represents a logical unit of work performed in a database.

These transactions have the characteristics of ACID, which represent four characteristics: atomicity, consistency, isolation, and persistence.

Now let's take a closer look at each characteristic.

{:data-align="center"}

<!-- outline-end -->

## Atomicity

Transactions must remain consistent with all tasks performed or nothing done.

This means that if all tasks are successfully completed, the transaction must be successfully completed, and if even one task fails, it must be rolled back to its previous state.

### Consistency

The database must remain consistent after the transaction is completed.

The consistency of the database must not change before and after the transaction is performed.

In other words, transactions must ensure the integrity of the database.

### Isolation

When multiple transactions are performed at the same time, each transaction must be performed independently without being affected by the actions of the other transactions.

In other words, there should be no interference between transactions, and each transaction should not be able to see the actions of other transactions.

### DURABILITY

Once a transaction is complete, changes made by that transaction must be permanently reflected in the database.

This means that even if the system fails, the database must retain its changes and be recoverable.

### The Importance of Transactions

Transactions play an important role in ensuring the integrity of the database and maintaining the reliability and consistency of the database system.

Transactions that comply with these ACID characteristics ensure that the database system operates reliably and ensures the integrity of the data.

## at the end of the day

A transaction represents a logical unit of action in a database and has the characteristic ACID.

These characteristics ensure that the database system operates reliably and the integrity of the data is maintained.

When designing and operating a database, it is critical to consider the nature of the transaction.

Thank you!
