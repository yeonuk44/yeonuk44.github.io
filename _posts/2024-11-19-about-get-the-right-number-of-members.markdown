---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Get_The_Right_Number_Of_Members
title: Get the right number of members (with.MySQL)
# title: Get the right number of members (with.MySQL)
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
date: 2024-11-19 09:00:00 +0900
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

## This is an article about finding the number of members who meet the conditions (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

In the USER_INFO table, please write a SQL statement that will print out how many of the members who joined in 2021 are over 20 years old and under 29 years old.

Problem Description

The following is a USER_INFO table that contains membership information that you have signed up for a clothing shopping mall.

The USER_INFO table is structured as below, and USER_ID, GENDER, AGE, and JOINED represent the membership ID, gender, age, and date of joining, respectively.

#### USER_INFO Table

<!-- #### restrictions

- The length of a is not less than 1 but not more than 1,000,000.
- a[i] means the number written on the i+1th balloon.
- All numbers of a are integers greater than or equal to -1,000,000 and less than or equal to 1,000,000,000.
- All numbers of a are different -->

<!-- #### I/O Yes -->

| Column name | Type       | Nullable |
| ----------- | ---------- | -------- |
| USER_ID     | INTEGER    | FALSE    |
| GENDER      | TINYINT(1) | TRUE     |
| AGE         | INTEGER    | TRUE     |
| JOINED      | DATE       | FALSE    |

The GENDER column is empty or has a value of 0 or 1, where 0 represents a man and 1 represents a woman.

### problem solving

```sql
SELECT COUNT(USER_ID) AS USERS
FROM USER_INFO
WHERE YEAR(JOINED) = '2021' AND AGE >= 20 AND AGE <= 29;
```

#### Solution Description

The COUNT function was used to count the users who met the conditions.

I wrote the 2021 and age limit in the conditional statement and filtered it.
