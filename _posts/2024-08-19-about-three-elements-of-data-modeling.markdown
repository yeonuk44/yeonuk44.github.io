---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Three_Elements_Of_Data_Modeling
title: About three elements of data modeling
# title: About three elements of data modeling
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Data
# multiple tag entries are possible
tags: [data]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-19 09:00:00 +0900
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

## This article examines the three elements of data modeling.

Hello!

Data modeling is an important process of structuring data systematically and designing database systems.

In this process, there are three key factors that must be considered for successful data modeling.

Entities, properties, relationships.

In this post, we will learn more about these three factors that underlie data modeling.

{:data-align="center"}

<!-- outline-end -->

## Entities

### What is an entity?

An entity is a data object that needs to be managed in the database.

It is an independent object that exists in the real world, and it becomes an object that can store information in a database.

For example, customers, products, orders, etc. are entities.

### Features of the entity

- Independence: An entity exists independently through a unique identifier.
- Specificity: An entity represents a specific object and contains real data.
- Attribute Set: Each entity has multiple attributes to define its characteristics.

### Example of an entity

- Customer: Customer ID, Name, Contact, Address
- Product: Product ID, name, price, manufacturer
- Order: Order ID, Order Date, Customer ID, Product ID

## Attribute

### What are properties?

An attribute is a unit of information that represents the characteristics of an entity.

Each entity consists of multiple attributes, which gather to form specific information about the entity.

For example, the attributes of a customer entity include its name, contact, address, and so on.

### Type of property

- Simple Attribute: A single attribute that is no longer divisible. For example: name, date of birth
- Composite Attribute: A property composed of multiple sub-attributes, e.g. address (city, road name, zip code, etc.)
- Derived Attribute: Attribute calculated using other attributes, e.g. Total order amount (unit price × quantity)

### Example Properties

- Customer entity: Customer ID, name, contact, address
- Product entity: Product ID, name, price, manufacturer
- Order entity: Order ID, Order Date, Customer ID, Product ID

## 관계 (Relationship)

### What is relationship?

Relationships represent interactions or associations between entities.

Data modeling defines relationships between entities to make data structures clearer and more systematic.

A relationship can occur between two or more entities.

### Types of relationships

- One-to-One: when one entity has only one association with another. e.g. employee and employee ID
- One-to-Many: when an entity has multiple entities associated. Example: Order with Customer
- Many-to-Many: When multiple entities are associated with multiple entities, e.g. students and lectures

### Examples of relationships

- Orders with customers: One customer can place multiple orders (one-to-many relationship)
- Products and Orders: One order may contain multiple products (many-to-many relationships)
- Employee and employee ID: Each employee has one employee ID (one-to-one relationship)

## at the end of the day

In data modeling, entities, properties, and relationships are both fundamental and very important.

Entities define the main objects to manage in the database, properties represent specific characteristics of each entity, and relationships clarify interactions between entities.

With a good understanding and utilization of these three elements, you can design an efficient and systematic data structure.

When designing a database system with data modeling, always keep these three elements in mind and build a clear and consistent data structure.

This will enable better data management and analysis, and ultimately contribute to the success of your business.
