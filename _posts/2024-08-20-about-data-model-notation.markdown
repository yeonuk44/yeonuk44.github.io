---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Data_Model_Notation
title: About data model notation
# title: About data model notation
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
date: 2024-08-20 09:00:00 +0900
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

## This article examines data model notation.

Hello!

Data model notation is an essential tool for a clear understanding of data structures.

In an era when data is at the heart of modern business, managing and leveraging data effectively is key to success.

Data modeling is an important process of structuring data systematically and designing databases.

In this process, the notation of visual representation of data plays a very important role.

Notations are very helpful in clearly understanding the data structure and designing an efficient database based on it.

In this post, we will learn about the types of data model notation and their respective features.

{:data-align="center"}

<!-- outline-end -->

## ERD (Entity-Relationship Diagram)

### What is ERD?

ERD is a diagram that visually represents the relationship between entities.

It is mainly used in the early stages of database design and is one of the basic tools in data modeling.

ERD clearly represents the data structure using entities, attributes, and relationships.

### Key components of ERD notation

- **Entity**: represented by a rectangle, representing the main object to be stored in the database.
- **Attribute**: represented by an ellipse, representing the characteristics of the entity.
- **Relationship**: Represented in diamond form, representing interactions between entities.
- **Line**: A line that connects entities to properties and relationships between entities.

### ERD Task Order

Effective writing of ERD requires a systematic approach.

Here is the ERD task sequence

1. **Collect and analyze requirements**: thoroughly analyze business requirements to identify key data to be managed in the database.
2. **Identify key entities**: Identify key objects that need to be managed in the database, i.e. customers, products, orders, etc.
3. **Define the attributes of an entity**: Define the main attributes, or attributes, that belong to each entity. For example, the attributes of a customer entity include its name, contact, address, etc.
4. **Define relationships between entities**: Define interactions or associations between entities. For example, define relationships between customers and orders.
5. **ER Diagrams **: Visualize entities, properties, relationships in a diagram, using symbols such as rectangles, ovals, diamonds, etc.
6. **Review and Correction**: Review the prepared ERD to ensure there are no logical errors or missing parts, and correct them if necessary.

### Advantages of ERD

- It is visually intuitive and easy to understand.
- The overall structure of the database can be clearly represented.
- It is easy to reflect business requirements.

## ML (Unified Modeling Language)

### What is UML?

UML is a modeling language mainly used when designing object-oriented systems.

However, it can also be useful in data modeling.

UML provides a variety of diagrams to allow visual representation of complex systems.

### Key components of UML notation

- **Class**: Similar to the table in the database, represents an entity. Classes consist of names, properties, and methods.
- **Attribute**: Indicates the properties of the class, each of which corresponds to a column in the database.
- **Relationship**: Indicates the association between classes, such as Association, Aggregation, and Composition.

### Advantages of UML

- It is easy to link with object-oriented design.
- Various diagrams allow a systematic representation of complex systems.
- A consistent modeling language is available throughout the development of the system.

## IDEF1X (Integration Definition for Information Modeling)

### What is IDEF1X?

IDEF1X is a data modeling notation developed by the U.S. Department of Defense designed to systematically represent complex data structures.

IDEF1X is based on entity relation modeling and is useful for large database design.

### Key components of IDEF1X notation

- **Entity**: expressed in boxes, represents objects to be managed in the database.
- **Attribute**: Writes inside the entity and defines the entity's characteristics.
- **Relationship**: Represented by arrows, it represents interactions between entities. IDEF1X represents identification and de-identification relationships separately.
- **Domain**: Defines the data type and constraints of the property.

### Advantages of IDEF1X

- It is suitable for large-scale database design.
- A normalization process of data may be clearly expressed.
- It helps to maintain consistency in the data structure.

## at the end of the day

Data model notation is an important tool in database design.

Various notations such as ERD, UML, and IDEF1X allow for a visual clarity of the data structure.

Each notation has its own characteristics and advantages, and it is important to select the appropriate notation according to the requirements of the system you want to design.

By understanding and utilizing data modeling notations well, you can maximize the efficiency of your database system.

This enables you to take full advantage of the value of your data and help your business succeed.

Actively utilize these notations in your database design process.

The data structure will become clearer, and better data management and analysis will be possible.
