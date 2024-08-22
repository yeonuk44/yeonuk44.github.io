---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Entity
title: About Entity
# title: About Entity
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
date: 2024-08-22 09:00:00 +0900
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

## This is an article about Entity.

Hello!

Hello!

Today, we're going to talk about one of the key concepts of database design: **Entity**.

Entities play an important role in databases and are essential for managing and organizing data systematically.

So let's take a closer look at what an entity is, why it's important, and how it's used.

{:data-align="center"}

<!-- outline-end -->

## What is an entity?

### Definition

An entity is an entity or object that you want to manage in a database.

It can be a physical object, it can be a conceptual or logical object. For example, in a corporate database, employees, departments, projects, etc. can be entities.

### Example

- **Customer**: An entity that contains information such as customer ID, name, contact information, address, etc.
- **Product**: An entity that contains information such as product ID, name, price, manufacturer, etc.
- **Order**: An entity containing information such as order ID, order date, customer ID, product ID, etc.

## Components of an entity

### Attribute

An attribute is a unit of information that represents the characteristics of an entity.

Each entity consists of multiple attributes, which combine to form specific information about the entity.

For example, the attributes of a customer entity include its name, contact information, address, and so on.

- **Basic attribute (Simple Attribute)**: A single attribute that is no longer divisible. Example: Name, Date of Birth
- **Composite Attribute**: Properties composed of multiple sub-attributes, e.g. address (city, road name, zip code, etc.)
- **Derived Attributes**: Attributes calculated using other attributes. e.g. Total order amount (unit price × quantity)

### Primary Key

A default key is a set of attributes or attributes used to uniquely identify each instance within an entity.

The default key requires every instance of an entity to have a unique value, allowing you to quickly search for a particular entity within the database.

### Foreign Key

Foreign keys refer to the default key of an entity that has different attributes.

This represents the relationship between entities and plays an important role in maintaining the integrity of the database.

## The Importance of Entertainment

### Structuring data

Entities play an important role in structuring data systematically.

This allows data within the database to be logically organized and efficiently retrieved and managed for the information it needs.

### Ensuring Data Integrity

An entity is essential to maintaining the integrity of the database.

Primary and foreign keys ensure data consistency and accuracy.

This increases the reliability of the database and prevents data loss or duplication.

### Reflect business logic

Entities play an important role in reflecting business logic in database design.

For example, entities such as customers, products, and orders can apply real business operations to database structures.

This enables databases to effectively support business requirements.

## Enterprise Design Considerations

### a clear definition

When designing an entity, you must clearly define what each entity represents.

This is important to accurately reflect the purpose and business requirements of the database.

### Select properties

You must carefully select the properties to be included in each entity.

Properties should represent the attributes of the entity well, and it is recommended that you exclude properties that are not required.

### Key settings

The primary and foreign keys must be properly set to maintain the integrity of the database.

The primary key must satisfy uniqueness and minimality, and the foreign key must accurately reflect the relationship between entities.

## at the end of the day

An entity is a key component of database design and plays an important role in managing data systematically and reflecting business logic.

If you understand and design the entity and its components, its properties, primary keys, and foreign keys, you can build an efficient and reliable database system.

Always keep the importance of the entity in mind when designing a database, and create a systematic and logical data model.

Now I hope you have a good understanding of the entity as well.

In the next post, we will talk about the relationship between entities and how to design it effectively.

Please look forward to it!
