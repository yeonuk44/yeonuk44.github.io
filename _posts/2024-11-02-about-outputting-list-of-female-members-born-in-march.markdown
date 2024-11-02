---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Outputting_List_Of_Female_Members_Born_In_March
title: Outputting a list of female members born in March (with. MySQL)
# title: Outputting a list of female members born in March (with. MySQL)
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
date: 2024-11-02 09:00:00 +0900
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

## Outputting a list of female members born in March (with. MySQL)

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

In the MEMBER_PROFILE table, please write a SQL statement that looks up the ID, name, gender, and date of birth of a female member whose birthday is March.

At this time, if the phone number is NULL, please exclude it from the output target and arrange the results in ascending order based on the member ID.

The following is the MEMBER_PROFILE table that contains the membership information of the restaurant review site.

The MEMBER_PROFILE table is as follows, and MEMBER_ID, MEMBER_NAME, TLNO, GENDER, DATE_OF_BIRTH stands for Member ID, Member Name, Member Contact, Gender, and Birth Date.

#### ECOLI_DATA table

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

| Column name   | Type         | Nullable |
| ------------- | ------------ | -------- |
| MEMBER_ID     | VARCHAR(100) | FALSE    |
| MEMBER_NAME   | VARCHAR(50)  | FALSE    |
| TLNO          | VARCHAR(50)  | TRUE     |
| GENDER        | VARCHAR(1)   | TRUE     |
| DATE_OF_BIRTH | DATE         | TRUE     |

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
SELECT MEMBER_ID, MEMBER_NAME, GENDER, DATE_FORMAT(DATE_OF_BIRTH, '%Y-%m-%d') AS DATE_OF_BIRTH
FROM MEMBER_PROFILE
WHERE SUBSTR(DATE_OF_BIRTH, 6,2) = '03' AND GENDER = 'W' AND TLNO IS NOT NULL ORDER BY MEMBER_ID;
```

#### Solution Description

This SQL query queries the information of members who meet certain conditions and returns the results sorted by member ID.

The query extracts data from the MEMBER_PROFILE table, and the main components are as follows.

First, the SELECT section specifies the columns to look up.

MEMBER_ID is the unique identifier of the member, MEMBER_NAME is the name of the member, GENDER is gender, DATE_FORMAT ('%Y-%m-%d') AS DATE_OF_BIRTH converts birthdate into 'YYY-Y-MM-DD' format and outputs it.

By doing this, the date of birth appears in a consistent format.

Next, the FROM section specifies the default table for which the query should be executed.

In this case, the MEMBER_PROFILE table is used.

The WHERE section then sets specific conditions to filter the required data.

SUBSTR (DATE_OF_BIRTH, 6, 2) = '03' selects only members whose birth date is '03' (i.e., March).

GENDER = 'W' selects only members of gender.

TLNOIS NOT NULL selects only members whose phone numbers exist.

These conditions allow you to look up only members who were born in March, are female, and have a phone number registered.

Finally, sort the results through the ORDER BY clause.

Sort by MEMBER_ID, and sort the results in order of the member ID.

This allows you to see the results sorted in order of membership ID.

##### Conclusion

This query allows you to look up the IDs, names, genders, and birth dates of members born in March, female, and registered phone numbers.

This makes it easy to grasp the information of members who meet certain conditions.
