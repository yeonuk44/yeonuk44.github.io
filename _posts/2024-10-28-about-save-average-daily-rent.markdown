---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Save_Average_Daily_Rent
title: Save average daily rent (with).MySQL)
# title: Save average daily rent (with).MySQL)
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
date: 2024-10-28 09:00:00 +0900
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

## Here's a look at the average daily rental fee (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

In the CAR_RENTAL_COMPANY_CAR table, please write a SQL statement that outputs the average daily rental fee for cars with car type 'SUV'.

At this time, the average daily rental fee should be rounded up to the first decimal place, and the column name should be AVERAGE_FEE.

The following is a CAR_RENTAL_COMPANY_CAR table that contains information about cars being rented by a car rental company.

The CAR_RENTAL_COMPANY_CAR table is structured as follows, and CAR_ID, CAR_TYPE, DAILY_FEE, and OPTIONS represent the car ID, car type, daily rental fee (KRW), and car option list, respectively.

The types of cars are Sedan, SUV, Vans, Truck, and Limousine. The list of car options is a list of keywords separated by commas (',') (e.g., 'heated seat,' 'smart key,' and 'parking sensor,' and the keywords are 'parking sensor,' 'smart key,' 'navigation,' 'ventilated seat,' 'heated seat,' 'rear camera,' and 'leather seat.'

#### Input/output Examples

| Column name | Type         | Nullable |
| ----------- | ------------ | -------- |
| CAR_ID      | INTEGER      | FALSE    |
| CAR_TYPE    | VARCHAR(255) | FALSE    |
| DAILY_FEE   | INTEGER      | FALSE    |
| OPTIONS     | VARCHAR(255) | FALSE    |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### problem solving

```sql
SELECT ROUND(AVG(DAILY_FEE)) AS AVERAGE_FEE
FROM CAR_RENTAL_COMPANY_CAR
GROUP BY CAR_TYPE HAVING CAR_TYPE = 'SUV'
```

#### Solution Description

This SQL query calculates and returns the average daily rental fee for a particular type of car.

The query extracts data from the CAR_RENTAL_COMPANY_CAR table, and the main components are as follows.

First, in the SELECT section, the calculated average daily rate is rounded up and outputted under the alias AVERAGE_FEE.

ROUND(AVG(DAILY_FEE)) AS AVERAGE_FEE obtains the average value of the DAILY_FEE column and returns it in integer form by rounding off the decimal point.

The FROM section then specifies the default table on which to run the query.

In this case, the CAR_RENTAL_COMPANY_CAR table is used.

Next, the GROUP BY section groups the data based on the CAR_TYPE column.

Allow the average daily rental fee to be calculated for each type of car.

Finally, the HAVING section selects only groups that meet specific conditions among grouped data.

HAVING CAR_TYPE = 'SUV' selects only groups with car type 'SUV'.

This condition allows you to calculate and return only the average daily fee for an SUV.

##### Conclusion

This query allows you to look up the average daily rental fee for SUV-type cars.

This will give you insight into the rental fee of the SUV.
