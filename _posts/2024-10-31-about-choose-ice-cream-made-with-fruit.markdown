---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Choose_Ice_Cream_Made_With_Fruit
title: Choose ice cream made with fruit (with.MySQL)
# title: Choose ice cream made with fruit (with.MySQL)
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
date: 2024-10-31 09:00:00 +0900
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

## This is an article about fruit ice cream selection (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Please write a SQL statement that inquires about the taste of ice cream, which has a total order of more than 3,000 ice cream in the first half of the year and whose main ingredient is fruit, in the order of the total order.

The following are the FIRST_HALF table with order information for the first half of the ice cream shop and the ICECREAM_INFO table with information on ice cream ingredients.

The structure of the FIRST_HALF table is as follows, and SHIPMENT_ID, FLAVOR, and TOTAL_ORDER represent the shipping number from the ice cream factory to the ice cream store, the ice cream flavor, and the total order volume of ice cream in the first half of the year, respectively.

The default key in the FIRST_HALF table is FLAVOR.

#### FIRST_HALF Table Structure

| NAME        | TYPE       | NULLABLE |
| ----------- | ---------- | -------- |
| SHIPMENT_ID | INT(N)     | FALSE    |
| FLAVOR      | VARCHAR(N) | FALSE    |
| TOTAL_ORDER | INT(N)     | FALSE    |

The ICECREAM_INFO table structure is as follows, and FLAVOR and INGREDITENT_TYPE represent the ice cream flavor and the ingredient type of ice cream, respectively.

In INGREDIENT_TYPE, if the main ingredient of the ice cream is sugar, it is entered as sugar, and if the main ingredient of the ice cream is fruit, it is entered as fruit_based.

The default key for ICECREAM_INFO is FLAVOR.

The FLAVOR in the ICECREAM_INFO table is the foreign key in the FLAVOR in the FIRST_HALF table.

#### ICECREAM_INFO Table Structure

| NAME            | TYPE       | NULLABLE |
| --------------- | ---------- | -------- |
| FLAVOR          | VARCHAR(N) | FALSE    |
| INGREDIENT_TYPE | VARCHAR(N) | FALSE    |

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
SELECT ICECREAM_INFO.FLAVOR
FROM ICECREAM_INFO, FIRST_HALF
WHERE ICECREAM_INFO.FLAVOR = FIRST_HALF.FLAVOR AND FIRST_HALF.TOTAL_ORDER > 3000 AND ICECREAM_INFO.INGREDIENT_TYPE = 'fruit_based'
ORDER BY FIRST_HALF.TOTAL_ORDER DESC;
```

#### Solution Description

This SQL query queries ice cream flavors that meet certain conditions and returns ordered results in order of order.

The query extracts data from the ICECREAM_INFO table and the FIRST_HALF table, and the main components are as follows.

First, the SELECT section specifies the columns to look up.

ICECREAM_INFO.FLAVOR stands for ice cream flavor, which outputs as a result.

The FROM section then specifies the default table on which to run the query.

Use two tables, ICECREAM_INFO and FIRST_HALF.

Specifies explicit join conditions to query these two tables at the same time.

Next, in the WHERE section, you set specific conditions to filter the data you need.

ICECREAM_INFO.FLAVOR = FIRST_HALF.FLAVOR is a condition in which the FLAVOR columns of both tables join the same row.

FIRST_HALF.TOTAL_ORDER > 3000 is a condition for selecting ice cream flavors with orders exceeding 3000 in the first half of the year.

ICECREAM_INFO.INGREDIENT_TYPE = 'fruit_based' is a condition for selecting ice cream flavors using fruit-based ingredients.

These conditions allow you to select only ice cream flavors using fruit-based ingredients, with orders exceeding 3000 in the first half of the year.

Finally, sort the results through the ORDER BY clause.

Sort by First_HALF.TOTAL_ORDER DESC, and sort the results in order of high order.

This allows you to check the results in order from the high-order ice cream flavor.

##### Conclusion

This query allows you to view ice cream flavors using fruit-based ingredients in order, with orders exceeding 3000 during the first half of the year.

This makes it easy to identify popular fruit-based ice cream flavors.
