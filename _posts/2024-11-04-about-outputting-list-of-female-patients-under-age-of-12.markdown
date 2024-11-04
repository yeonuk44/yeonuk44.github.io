---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Outputting_List_Of_Female_Patients_Under_Age_Of_12
title: Outputting a list of female patients under the age of 12 (with. MySQL)
# title: Outputting a list of female patients under the age of 12 (with. MySQL)
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
date: 2024-11-04 09:00:00 +0900
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

## This article is about printing a list of female patients under the age of 12 (with. MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

In the PATIENT table, please write a SQL statement that looks up the patient name, patient number, gender code, age, and phone number of a female patient under the age of 12.

If you don't have a phone number, please print it out as 'NONE' and arrange the results in descending order based on age, and if you are of the same age, arrange it in ascending order based on patient name.

The following is a PATIENT table containing patient information registered in a general hospital.

The PATIENT table is as follows, and PT_NO, PT_NAME, GEND_CD, AGE, and TLNO mean patient number, patient name, gender code, age, and phone number, respectively.

#### PATIENT Table

<!-- | NAME           | TYPE    | NULLABLE |
| -------------- | ------- | -------- |
| ID             | INTEGER | FALSE    |
| PARENT_ID      | INTEGER | TRUE     |
| SIZE_OF_COLONY | INTEGER | FALSE    | -->

<!-- #### restrictions

- The length of a is not less than 1 but not more than 1,000,000.
- a[i] means the number written on the i+1th balloon.
- All numbers of a are integers greater than or equal to -1,000,000 and less than or equal to 1,000,000,000.
- All numbers of a are different -->

<!-- #### I/O Yes -->

| Column name | Type        | Nullable |
| ----------- | ----------- | -------- |
| PT_NO       | VARCHAR(10) | FALSE    |
| PT_NAME     | VARCHAR(20) | FALSE    |
| GEND_CD     | VARCHAR(1)  | FALSE    |
| AGE         | INTEGER     | FALSE    |
| TLNO        | VARCHAR(50) | TRUE     |

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
SELECT PT_NAME, PT_NO, GEND_CD, AGE, IFNULL(TLNO, "NONE") AS TLNO
FROM PATIENT
WHERE AGE <= 12 AND GEND_CD = "W"
ORDER BY AGE DESC, PT_NAME ASC
```

#### Solution Description

NULL values were processed through the IFNULL function, and age and gender conditions were grouped into AND.

Sorting was in descending order by age, and if the age was the same, sorted in ascending order by patient name.
