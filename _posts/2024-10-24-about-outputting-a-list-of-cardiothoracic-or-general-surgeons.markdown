---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Outputting_A_List_Of_Cardiothoracic_Or_General_Surgeous
title: Outputting a list of cardiothoracic or general surgeons (with.MySQL)
# title: Outputting a list of cardiothoracic or general surgeons (with.MySQL)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: SQL
# multiple tag entries are possible
tags: [sql, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-24 09:00:00 +0900
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

## This article is about printing a list of cardiothoracic or general surgeons (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

In the DOCTOR table, please write a SQL statement that looks up the name, doctor ID, medical department, and employment date of the doctor whose medical department is a cardiothoracic surgeon (CS) or a general surgeon (GS).

At this time, please sort the results in descending order based on the employment date, and if the employment date is the same, sort them in ascending order based on the name.

#### Input/output Examples

| Column name | Type        | Nullable |
| ----------- | ----------- | -------- |
| DR_NAME     | VARCHAR(20) | FALSE    |
| DR_ID       | VARCHAR(10) | FALSE    |
| LCNS_NO     | VARCHAR(30) | FALSE    |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### problem solving

```sql
SELECT DR_NAME, DR_ID, MCDP_CD, DATE_FORMAT(HIRE_YMD, '%Y-%m-%d') AS HIRE_YMD
FROM DOCTOR
WHERE MCDP_CD = 'CS' OR MCDP_CD = 'GS' ORDER BY HIRE_YMD DESC, DR_NAME;
```

#### Solution Description

This SQL query queries the information of doctors in a particular department and returns the results sorted by the date of employment.

The query extracts data from the DOCTOR table, and the main components are as follows.

First, specify the columns to look up through the SELECT clause.

DR_NAME is the doctor's name, DR_ID is the doctor's unique identifier, MCDP_CD is the medical department code, DATE_FORMAT ('%YMD, %Y-%m-%d') AS HIRE_YMD converts the employment date to 'YYYY-MM-DD' format and outputs it.

By doing this, the employment date appears in a consistent format.

Next, the FROM section specifies the default table for which the query should be executed.

In this case, the DOCTOR table is used.

The WHERE section then sets specific conditions to filter the required data.

MCDP_CD = 'CS' OR MCDP_CD = 'GS' selects only doctors whose department code is 'CS' (Surgery) or 'GS' (General Surgery).

In this way, only doctors belonging to the surgery department and general surgery department can be referred to.

Finally, sort the results through the ORDER BY clause.

Sort by HIRE_YMD DESC and DR_NAME, with employment days in the latest order, and names in ascending order if they are the same.

This allows you to see the results sorted in order from recently hired doctors.

##### Conclusion

This query allows you to look up the names, IDs, clinic codes, and employment dates of doctors in Surgeons and General Surgeons in order of the latest employment dates.

This information is useful for analysis based on the doctor's employment date and department.
