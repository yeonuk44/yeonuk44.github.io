---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Sort_By_Multiple_Criteria
title: Sort by multiple criteria (with.MySQL)
# title: Sort by multiple criteria (with.MySQL)
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
date: 2024-11-15 09:00:00 +0900
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

## I learned about sorting by multiple criteria (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Please write a SQL statement that looks up the ID, name, and protection start date of all animals entering the animal shelter in order of name.

However, among animals with the same name, you must first show the animals that started protecting later.

Problem Description

The ANIMAL_INS table is a table that contains information about animals that have entered the animal shelter.

ANIMAL_INS table structures are as follows: ANIMAL_ID, ANIMAL_TYPE, DATETIME, INTAKE_CONDITION, NAME, SEX_UPON_INTAKE indicate the animal's ID, species, start date of protection, status, name, gender, and neutralization at the start of protection, respectively.

#### ANIMAL_INS table

<!-- #### restrictions

- The length of a is not less than 1 but not more than 1,000,000.
- a[i] means the number written on the i+1th balloon.
- All numbers of a are integers greater than or equal to -1,000,000 and less than or equal to 1,000,000,000.
- All numbers of a are different -->

<!-- #### I/O Yes -->

| NAME             | TYPE       | NULLABLE |
| ---------------- | ---------- | -------- |
| ANIMAL_ID        | VARCHAR(N) | FALSE    |
| ANIMAL_TYPE      | VARCHAR(N) | FALSE    |
| DATETIME         | DATETIME   | FALSE    |
| INTAKE_CONDITION | VARCHAR(N) | FALSE    |
| NAME             | VARCHAR(N) | TRUE     |
| SEX_UPON_INTAKE  | VARCHAR(N) | FALSE    |

### problem solving

```sql
SELECT ANIMAL_ID, NAME, DATETIME
FROM ANIMAL_INS
ORDER BY NAME, DATETIME DESC;
```

#### Solution Description

In the ANIMAL_INS table required in the problem, the ID, name, and protection start date of all animals were searched in order of name, and if there was an animal with the same name, it was printed to show the animal that started protection later.
