---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Classification_Of_Entities
title: About the characteristics of Entity
# title: About the characteristics of Entity
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
date: 2024-08-24 09:00:00 +0900
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

## This article examines the classification of Entity.

Hello!

Today, we're going to learn about the classification of **Entertainment**, an important concept in database design.

An entity is a basic component of a database, which can be categorized according to a number of criteria.

In this post, let's take a closer look at how we can categorize entities based on **EntityType** and **Entity Occurrence**.

{:data-align="center"}

<!-- outline-end -->

## Types of Entertainment (Tangible Entertainment vs Intangible Entertainment)

### Tangible Entities

#### Definition

A tangible entity represents a physical entity.

These entities are objects that can actually be observed or measured, and they have physical forms in the real world.

#### Example

- **Customer**: Contains information such as the customer's name, contact information, and address.
- **Product**: Contains information such as product name, price, manufacturer, etc.
- **Building**: Contains information on the address, size, purpose, etc. of the building.

#### Characteristics

- It is physically present, and can be observed directly in the real world.
- It mainly plays an important role in managing the company's assets and inventory.

### Intangible Entities

#### Definition

An intangible entity represents an entity that is not physically present but is conceptually important.

These entities have no physical form, but they are managed as important information in the database.

#### Example

- **Contract**: Includes information such as contract number, contract date, contract terms, etc.
- **Insurance**: Includes information such as insurance number, type of insurance, amount of insurance, etc.
- **Order**: Include information such as order number, order date, customer ID, product ID, etc.

#### Characteristics

- There is no physical form, but it plays an important role in the business process.
- It is mainly used in various fields such as finance, law, and administration.

## When an entity occurs (static entity vs dynamic entity)

### Static Entities

#### Definition

Static entity refers to an entity that does not change or fluctuate with time.

These entities rarely change once they are registered in the database.

#### Example

- **Country**: Contains information such as country code, country name, continent, etc.
- **Currency**: Contains information such as currency code, currency name, exchange rate, etc.
- **Product Category**: Contains information such as category ID, category name, etc.

#### Characteristics

- With little variation in the data, maintenance is relatively easy.
- It is primarily used as reference data.

### Dynamic Entities

#### Definition

Dynamic entity refers to an entity whose data changes frequently over time.

These entities are constantly changed by business activities or external factors.

#### Example

- **Order**: Information such as order status, order date, customer information, etc. will change frequently.
- **Customer**: Information such as the customer's address, contact information, and order history will change frequently.
- **Inventory**: Information such as inventory quantity, warehousing date, and release date will change frequently.

#### Characteristics

- Data changes frequently, so care must be taken to maintain database performance and consistency.
- It is primarily used as transaction data.

## at the end of the day

An entity is a key component of database design and can be categorized according to a variety of criteria.

Depending on the type, the entity can be classified into **typed entity** and **intangible entity** and **static entity** and **dynamic entity** depending on the time of occurrence.

This classification helps you understand and manage the characteristics of the entity when designing the database.

Build a more efficient and consistent data model by considering the type of entity and when it occurs when designing the database.

This will make it easier to manage and utilize your data.

I hope this post helped me understand the classification of the entity.
