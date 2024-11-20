---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Find_Python_Developer
title: Find Python Developer (with.MySQL)
# title: Find Python Developer (with.MySQL)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Sql
# multiple tag entries are possible
tags: [sql, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-11-20 09:00:00 +0900
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

## This article is about Python Developer Search (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

You want to query the information of a developer with Python skills in the DEVELOPER_INFOS table.

Please write a SQL statement that looks up the ID, email, name, and last name of a developer with Python skills.

Please arrange the results in ascending order based on the ID.

Problem Description

The DEVELOPER_INFOS table is a table that contains information about developers' programming skills.

The table structure of DEVELOPER_INFOS is as follows: ID, FIRST_NAME, LAST_NAME, EMAIL, SKILL_1, SKILL_2, and SKILL_3 mean ID, name, last name, email, first skill, second skill, and third skill, respectively.

#### USER_INFO Table

<!-- #### restrictions

- The length of a is not less than 1 but not more than 1,000,000.
- a[i] means the number written on the i+1th balloon.
- All numbers of a are integers greater than or equal to -1,000,000 and less than or equal to 1,000,000,000.
- All numbers of a are different -->

<!-- #### I/O Yes -->

| NAME       | TYPE       | UNIQUE | NULLABLE |
| ---------- | ---------- | ------ | -------- |
| ID         | VARCHAR(N) | Y      | N        |
| FIRST_NAME | VARCHAR(N) | N      | Y        |
| LAST_NAME  | VARCHAR(N) | N      | Y        |
| EMAIL      | VARCHAR(N) | Y      | N        |
| SKILL_1    | VARCHAR(N) | N      | Y        |
| SKILL_2    | VARCHAR(N) | N      | Y        |
| SKILL_3    | VARCHAR(N) | N      | Y        |

### problem solving

```sql
SELECT ID, EMAIL, FIRST_NAME, LAST_NAME
FROM DEVELOPER_INFOS
WHERE "Python" IN (SKILL_1, SKILL_2, SKILL_3)
ORDER BY ID;
```

#### Solution Description

This SQL query queries information from developers with specific skills and returns results sorted by developer ID.

The query extracts data from the DEVELOPER_INFOS table, and the main components are as follows.

First, the SELECT section specifies the columns to look up.

ID is the developer's unique identifier, EMAIL is the developer's email address, and FIRST_NAME and LAST_NAME are the developer's first and last names, respectively, and these four information are output as a result.

The FROM section then specifies the default table on which to run the query.

In this case, the DEVELOPER_INFOS table is used.

Next, in the WHERE section, you set specific conditions to filter the data you need.

"Python" IN (SKILL_1, SKILL_2, SKILL_3) selects any of the three technologies owned by the developer that contain "Python".

This allows only developers with Python technology to look up.

Finally, sort the results through the ORDER BY clause.

You can sort the result in ascending order based on the ID, in order of developer ID.

This query allows you to look up the ID, email, first name, and last name of developers with Python technology.

This makes it easy to identify information about developers with specific skills and can be useful for analysis or recruitment processes based on technical capabilities.
