---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Find_Coli_With_Specific_Traits
title: Find E. coli with specific traits (with.MySQL)
# title: Find E. coli with specific traits (with.MySQL)
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
date: 2024-12-02 09:00:00 +0900
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

## This article examines the search for E. coli (with.MySQL) with a specific trait.

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Please write a SQL statement that outputs the number (COUNT) of E. coli individuals that have trait 1 or 3 without trait 2.

If you have both traits 1 and 3, you can also include them if you have traits 1 or 3.

Problem Description

E. coli differentiates in a certain cycle, and the individual that started differentiation is called the parent individual, and the individual that differentiated is called the child individual.

The following is an ECOLI_DATA table containing information on E. coli cultured in the laboratory.

The structure of the ECOLI_DATA table is as follows: ID, PARENT_ID, SIZE_OF_COLONY, DIFFERENTION_DATE, and GENOTYPE represent the ID of the E. coli entity, the parent entity, the size of the entity, the date of differentiation, and the trait of the entity, respectively.

#### ECOLI_DATA table

<!-- #### restrictions

- The length of a is not less than 1 but not more than 1,000,000.
- a[i] means the number written on the i+1th balloon.
- All numbers of a are integers greater than or equal to -1,000,000 and less than or equal to 1,000,000,000.
- All numbers of a are different -->

<!-- #### I/O Yes -->

| Column name          | Type    | Nullable |
| -------------------- | ------- | -------- |
| ID                   | INTEGER | FALSE    |
| PARENT_ID            | INTEGER | TRUE     |
| SIZE_OF_COLONY       | INTEGER | FALSE    |
| DIFFERENTIATION_DATE | DATE    | FALSE    |
| GENOTYPE             | INTEGER | FALSE    |

The PARENT_ID of the first E. coli entity is a NULL value.

### problem solving

```sql
SELECT COUNT(*) AS COUNT
FROM ECOLI_DATA
WHERE (GENOTYPE & 2) != 2 AND ((GENOTYPE & 1) = 1 OR (GENOTYPE & 4) = 4);
```

#### Solution Description

This SQL query calculates and returns the number of E. coli data that meet certain conditions.

The query extracts data from the ECOLI_DATA table, and the main components are as follows.

First, the SELECT section specifies the value to look up.

COUNT(\*) AS COUNT calculates the number of records that meet the conditions and outputs the results under the alias COUNT.

This value represents the total number of E. coli data that meet the condition.

The FROM section then specifies the default table on which to run the query.

In this case, the ECOLI_DATA table is used.

Next, in the WHERE section, we use bit operations to set specific conditions and filter the data accordingly.

The first condition (GENOTYPE & 2)!= 2 selects a record that does not contain bits with a GENOTYPE value of 2.

Bit operation & performs bit-by-bit AND operation, and is selected only if the result of AND operation of 2 in the GENOTYPE value is not 2.

This means that the GENOTYPE value is not set to 1 at the bit position of 2.

The second condition is (GENOTYPE & 1) = 1 OR (GENOTYPE & 4) = 4.

This selects a record containing bits with a GENOTYPE value of 1 or 4.

(GENOTYPE & 1) = 1 condition means that the GENOTYPE value is set to 1 at the bit position of 1.

(GENOTYPE & 4) = 4 condition means that the GENOTYPE value is set to 1 in the bit position of 4.

If either of these conditions is satisfied, the record is selected.

This query calculates the number of E. coli data that meet the bit operation conditions and returns it to COUNT.

This allows us to analyze or statistically determine the frequency of E. coli data with specific genotype patterns.
