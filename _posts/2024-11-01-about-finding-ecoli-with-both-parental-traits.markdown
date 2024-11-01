---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Finding_EColi_With_Both_Parental_Traits
title: Finding E. coli with both parental traits (with.MySQL)
# title: Finding E. coli with both parental traits (with.MySQL)
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
date: 2024-11-01 09:00:00 +0900
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

## Finding E. coli with both parental traits (with. My)

## Finding E. coli with both parental traits (with.MySQL)

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Please write a SQL statement that outputs the ID of E. coli (ID), the trait of E. coli (GENOTYPE), and the trait of the parent E. coli (PARENT_GENOTYPE).

At this time, please sort the results in ascending order for the ID.

E. coli differentiates in a certain cycle, and the individual that started differentiation is called the parent individual, and the individual that differentiated is called the child individual.

The following is an ECOLI_DATA table containing information on E. coli cultured in the laboratory.

The structure of the ECOLI_DATA table is as follows: ID, PARENT_ID, SIZE_OF_COLONY, DIFFERENTION_DATE, and GENOTYPE represent the ID of the E. coli entity, the parent entity, the size of the entity, the date of differentiation, and the trait of the entity, respectively.

#### ECOLI_DATA table

| NAME           | TYPE    | NULLABLE |
| -------------- | ------- | -------- |
| ID             | INTEGER | FALSE    |
| PARENT_ID      | INTEGER | TRUE     |
| SIZE_OF_COLONY | INTEGER | FALSE    |

The PARENT_ID of the first E. coli entity is a NULL value.

<!-- #### restrictions

- The length of a is not less than 1 but not more than 1,000,000.
- a[i] means the number written on the i+1th balloon.
- All numbers of a are integers greater than or equal to -1,000,000 and less than or equal to 1,000,000,000.
- All numbers of a are different -->

<!-- #### I/O Yes -->

<!--
| Column name | Type         | Nullable |
| ----------- | ------------ | -------- |
| CAR_ID      | INTEGER      | FALSE    |
| CAR_TYPE    | VARCHAR(255) | FALSE    |
| DAILY_FEE   | INTEGER      | FALSE    |
| OPTIONS     | VARCHAR(255) | FALSE    | -->

<!-- | a                                     | result |
| ------------------------------------- | ------ |
| [9,-1,-5]                             | 3      |
| [-16,27,65,-2,58,-92,-71,-68,-61,-33] | 6      | -->

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### problem solving

```sql
SELECT A.ID, A.GENOTYPE, B.GENOTYPE AS PARENT_GENOTYPE
FROM ECOLI_DATA A, ECOLI_DATA B
WHERE A.PARENT_ID = B.ID AND B.GENOTYPE & A.GENOTYPE = B.GENOTYPE
ORDER BY ID;
```

#### Solution Description

This SQL query returns a pair of records with a specific parent-child relationship in the _E. coli_ data.

The query references the data twice in the same table, 'ECOLI_DATA', and the main components are as follows.

First, in the 'SELECT' section, specify the columns to look up.

'A.ID' is the unique identifier of the child _E. coli_ record, 'A.GENOTYPE' is the genotype information of the child _E. coli_, and 'B.GENOTYPE AS PARENT_GENOTYPE' includes the genotype information of the parent _E. coli_ as the alias 'PARENT_GENOTYPE' in the result.

This allows you to print out the genotype information of your child and parents together.

The 'FROM' section then specifies the default table for which the query will run.

Here, we refer to the same 'ECOLI_DATA' table twice, and we alias 'A' and 'B' for each reference.

'A' represents the data of the child _E. coli_ and 'B' represents the data of the parent _E. coli_.

Next, in the 'WHERE' section, we filter the necessary data by setting parent-child relationships and genotype conditions.

- The 'A.PARENT_ID = B.ID' condition selects when the 'PARENT_ID' value of the 'A' table matches the 'ID' value of the 'B' table. This means that the 'A' record is a child of the 'B' record.
- The 'B.GENOTYPE & A.GENOTYPE = B.GENOTYPE' condition selects when the genotype of the parent _E. coli_ ('B') is part of the genotype of the child _E. coli_ ('A') The bit AND operation verifies that the parent's genotype is included in the child's genotype and is included in the result only if this condition is met.

Finally, sort the results through the 'ORDER BY ID' section.

You can sort the child _E.coli_ record in ascending order based on the 'ID' of the child _E.coli_ record, and see the results in order of ID.

This query allows you to query the ID and genotype information of a pair of _E. coli_ records that have a specific parent-child relationship and whose parent's genotype is included in your child's genotype.

This can be useful for analyzing the inheritance patterns of genotypes or the relationship between specific genotypes.
