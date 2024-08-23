---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_The_Characteristics_Of_Entity
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
date: 2024-08-23 09:00:00 +0900
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

## This article examines the characteristics of Entity.

Hello!

Today, we're going to learn about the fundamental concepts of database design: **Entity**.

Entities play an important role in databases and are essential for managing and organizing data systematically.

With a better understanding of the characteristics of the entity, you can design more efficient and consistent data models.

Let's take a look at the main characteristics of the entity one by one.

{:data-align="center"}

<!-- outline-end -->

## Uniqueness

### Description

The entity must represent a unique object in the database.

This means that each instance of the entity must have a unique identifier so that it can be distinguished from each other.

This identifier is defined as **Primary Key**.

### Example

- **Customer entity**: Customer ID must be unique, which can distinguish each customer.
- **Product entity**: The product ID must be unique, which allows you to identify each product.

## Attributes

### Description

An entity consists of multiple properties.

Attributes represent attributes of an entity, each of which contains specific information about the entity.

Attributes are important components that describe the data elements of an entity.

### Example

- **Customer entity**: It may have properties such as name, contact, address, etc.
- **Product entity**: may have attributes such as name, price, manufacturer, etc.

## 관계 (Relationships)

### Description

An entity can relate to other entities.

These relationships indicate associations between entities within the database.

Relationships are important for maintaining data consistency and ensuring connectivity between data.

### Example

- **Relationship between customer and order**: Customer can place multiple orders, each of which belongs to one customer.
- **Relationship between product and order**: One order may contain multiple products, each of which may be included in multiple orders.

## Identifiability

### Description

The entity must be uniquely identifiable.

This means that each entity instance must have its own properties.

Ensuring this identifiability is **default key**.

A default key is a set of attributes or attributes that uniquely identify each instance of an entity.

### Example

- **Customer entity**: Customer ID is the default key to uniquely identify each customer.
- **Order entity**: Order ID is the default key to uniquely identify each order.

## Data Integrity

### Description

The entity must maintain data integrity.

This means that the entity's data remains accurate and consistent.

To maintain data integrity, you must set the appropriate **Constraint** within the database.

### Example

- **Customer entity**: The customer's email address must be unique and non-overlapping.
- **Product entity**: The price of the product must be greater than zero and cannot be negative.

## Abstraction

### Description

The entity abstracts real-world objects so that they can be managed within a database.

Abstraction is the process of simplifying complex real-world objects to make them easier to manage within a database.

### Example

- **Customer entity**: Abstracts real-world customers and manages them with attributes such as name, contact, address, etc. within the database.
- **Product entity**: Abstracts real-world products and manages them with attributes such as name, price, manufacturer, etc. within the database.

## at the end of the day

An entity is the basic unit of database design, with features such as uniqueness, attributes, relationships, identifiability, data integrity, abstraction, and more.

Understanding and leveraging these features will help you design more efficient and consistent data models.

Designing a database that takes into account the characteristics of the entity will make it much easier to manage and utilize the data.

In this post, we learned about the main characteristics of the entity.

In the next post, we will talk about the relationship between entities and how to design it effectively.

Please look forward to it!
