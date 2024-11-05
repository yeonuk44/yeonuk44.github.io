---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Outputting_List_Of_Books_That_Meet_The_Conditions
title: Outputting a list of books that meet the conditions (with.MySQL)
# title: Outputting a list of books that meet the conditions (with.MySQL)
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
date: 2024-11-05 09:00:00 +0900
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

## This article is about printing a list of books that meet the conditions (with.MySQL).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

In the BOOK table, please find a list of books belonging to the 'Humanities' category published in 2021 and write a SQL statement that outputs the book ID (BOOK_ID) and the date of publication (PUBLISHED_DATE).
Please arrange the results in ascending order based on the publication date.

Problem Description
The following is a book table of books sold at a bookstore.

The Book Table is a table containing information on each book and has the following structure.

#### BOOK TABLE

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

| Column name    | Type       | Nullable | Description                                              |
| -------------- | ---------- | -------- | -------------------------------------------------------- |
| BOOK_ID        | INTEGER    | FALSE    | 도서ID                                                   |
| CATEGORY       | VARCHAR(N) | FALSE    | Category (Economy, Humanities, Novels, Life, Technology) |
| AUTHOR_ID      | INTEGER    | FALSE    | 저자ID                                                   |
| PRICE          | INTEGER    | FALSE    | Sale Price (KRW)                                         |
| PUBLISHED_DATE | DATE       | FALSE    | 출판일                                                   |

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
SELECT BOOK_ID, DATE_FORMAT(PUBLISHED_DATE, '%Y-%m-%d') AS PUBLISHED_DATE
FROM BOOK
WHERE SUBSTR(PUBLISHED_DATE, 1, 4) = '2021' AND CATEGORY = '인문'
```

#### Solution Description

Use the DATE_FORMAT function to format the date in the required format.

After filtering 2021 using SUBSTR to see if it meets the conditions, check whether the category is humanities and print it out with AND.
