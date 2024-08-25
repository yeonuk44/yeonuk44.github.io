---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Attributes
title: About Attributes
# title: About Attributes
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
date: 2024-08-25 09:00:00 +0900
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

## This is an article about attributes.

Hello!

Today, we're going to talk about one of the key elements of database design: **Attribute**.

Attributes are the basic elements that represent the characteristics of data within a database, representing the specific information each entity has.

In this post, let's take a closer look at what properties are, and how they are defined and used.

{:data-align="center"}

<!-- outline-end -->

## What are properties?

### Definition

An attribute is a data element that represents the characteristics of an entity.

Each entity consists of multiple attributes, which come together to form specific information about the entity.

For example, the attributes of a student's entity may include the student's student number, name, and major.

### Example

- **Student**: You may have attributes such as student number, name, major, grade, etc.
- **Product**: Properties such as product code, product name, price, manufacturer, etc.
- **Order**: You may have attributes such as order number, order date, customer ID, product ID, etc.

## Types of properties

### Simple Attribute

#### Definition

The default property is a single property that is no longer divisible.

In other words, it represents the smallest unit of data that properties can no longer be subdivided or decomposed.

#### Example

- **Student ID for students**: Student numbers are a single attribute that can no longer be broken down or subdivided.
- **Price of the product**: Price is a basic property expressed as a single value.

### Composite Attributes

#### Definition

A composite property is a property that consists of multiple sub-attributes.

That is, the property consists of several parts, which together make up the value of the property.

#### Example

- **Address**: Addresses may consist of several sub-properties, such as city, distance, zip code, etc.
- **Name**: Names can consist of several sub-properties, such as last name, first name, and middle name.

### Derived Attributes

#### Definition

Derivative properties are properties calculated using other properties.

In other words, the value of an attribute is determined by the operation or function of the other attributes.

#### Example

- **Total Order Amount**: The total order amount is calculated by multiplying the price and quantity of the product you ordered.
- **Age**: Age may be calculated based on date of birth compared to current date.

## at the end of the day

Properties are the basic elements that define the characteristics of data in a database, representing the information each entity has.

Designing a database by appropriately leveraging different kinds of properties, such as basic properties, composite properties, and derivative properties, enables more efficient and flexible data models to be built.

I hope this post helped me understand the properties.

Thank you!
