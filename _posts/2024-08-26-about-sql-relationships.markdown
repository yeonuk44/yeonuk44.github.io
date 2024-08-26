---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_SQL_Relationships
title: About SQL Relationships
# title: About SQL Relationships
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
date: 2024-08-26 09:00:00 +0900
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

## This article examines the relationship between SQL.

Hello!

Today, we're going to talk about relationships in Structured Query Language (SQL).

SQL is a powerful language used to manage and manipulate data in databases, and plays an important role in representing and processing relationships between data in relational databases.

In this post, we will look at the main concepts related to how to express relationships in SQL.

{:data-align="center"}

<!-- outline-end -->

## relational database model

### Overview

A relational database model is a method of storing and managing data in a table format.

In this model, each table represents an entity, and it organizes and manages data through the relationships between the tables.

### Example

- **Student Table**: Store information such as student's number, name, major, etc.
- **Subject table**: Store information such as the subject's code, name, and professor in charge.
- **Enrollment table**: Saves the course relationship between the student and the subject.

## How to express a relationship

### Primary Key

The default key is a property used to uniquely identify records in each table.

The default key must be able to uniquely identify each record in the table and cannot have a NULL value.

```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(50),
    Major VARCHAR(50)
);

CREATE TABLE Subjects (
    SubjectID INT PRIMARY KEY,
    Name VARCHAR(50),
    Professor VARCHAR(50)
);
```

### Foreign Key

Foreign keys are properties that refer to the default keys in other tables.

This allows you to establish and manage relationships between tables.

```sql
CREATE TABLE Enrollments (
    EnrollmentID INT PRIMARY KEY,
    StudentID INT,
    SubjectID INT,
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (SubjectID) REFERENCES Subjects(SubjectID)
);
```

## Relationship Type

### One-to-one relationship

A relationship in which only one entity's record is associated with another entity's record.

### One-to-Many Relationship

A relationship in which one entity's records are associated with several other entities' records.

### Many-to-Many Relationship

A relationship in which a number of entities' records are associated with several other entities' records.

This relationship is implemented using an intermediate table.

## Working with relationships in SQL

### JOIN

Join is used to search and combine data by connecting two or more tables.

```sql
SELECT Students.Name, Subjects.Name
FROM Students
JOIN Enrollments ON Students.StudentID = Enrollments.StudentID
JOIN Subjects ON Enrollments.SubjectID = Subjects.SubjectID;
```

### Subquery

Subqueries are subqueries that are used to retrieve and use the results of other queries.

```sql
SELECT Name
FROM Students
WHERE StudentID IN (SELECT StudentID FROM Enrollments WHERE SubjectID = 1);
```

## at the end of the day

SQL uses relational database models to represent and process relationships between data.

Use default and foreign keys to establish relationships between tables, and use join and subquery to retrieve and manipulate data.

Understanding relational database models and effectively addressing relationships in SQL requires understanding of primary keys, foreign keys, and different types of relationships.

This allows us to efficiently deal with complex relationships in the database and extract the desired information accurately.

In this post, we took a brief look at the relationship in SQL.

In the next post, we'll go into more detail about the join and subquery in SQL.

I'd appreciate it if you could continue to be interested!
