---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Check_Used_Transaction_Comments_That_Meet_The_Conditions
title: Check used transaction comments that meet the conditions (with.MySQL)
# title: Check used transaction comments that meet the conditions (with.MySQL)
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
date: 2024-10-25 09:00:00 +0900
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

## This is an article about inquiring about secondhand transaction comments (with.MySQL) that meet the conditions.

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

In the USED_GOODS_BOARD and USED_GOODS_REPLY tables, please write a SQL statement that looks up the title, post ID, comment ID, comment writer ID, comment content, and comment writing date of October 2022.

Please sort the results in ascending order based on the comment writing date, and if the comment writing date is the same, please sort in ascending order based on the title of the post.
0

#### Input/output Examples

| Column name | Type          | Nullable |
| ----------- | ------------- | -------- |
| REPLY_ID    | VARCHAR(10)   | FALSE    |
| BOARD_ID    | VARCHAR(5)    | FALSE    |
| WRITER_ID   | VARCHAR(50)   | FALSE    |
| CONTENTS    | VARCHAR(1000) | TRUE     |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### problem solving

```sql
SELECT B.TITLE, B.BOARD_ID, R.REPLY_ID, R.WRITER_ID, R.CONTENTS, DATE_FORMAT(R.CREATED_DATE, '%Y-%m-%d') AS CREATED_DATE
FROM USED_GOODS_BOARD AS B
JOIN USED_GOODS_REPLY AS R ON B.BOARD_ID = R.BOARD_ID
WHERE SUBSTR(B.CREATED_DATE, 1, 7) = '2022-10' ORDER BY R.CREATED_DATE, B.TITLE
```

#### Solution Description

This SQL query looks up posts on used merchandise bulletins created on a specific date and comments on those posts.

This query outputs the result by joining two tables, USED_GOODS_BOARD and USED_GOODS_REPLY.

Below is a detailed description of each part of the query.

First, in the SELECT section, we specify the columns that we want to look up.

B.TITLE converts the title of the post, B.BOARD_ID converts the unique identifier of the post, R.REPLY_ID converts the commenter's ID, R.CONTENS converts the content of the comment, and DATE_FORMAT ('%Y-%m-%d') AS CREATED_DATE converts the date of writing the comment into 'YYYY-MM-DD' format.

The FROM section then specifies the default table on which to run the query.

In this case, set the USED_GOODS_BOARD table to the default table.

Next, join the USED_GOODS_REPLY table and the USED_GOODS_BOARD table through the JOIN clause.

The condition of the join is ONB.BOARD_ID = R.BOARD_ID, based on the BOARD_ID column of both tables.

This allows you to link the comments on each post.

In the WHERE section, you can specify a condition to look up only posts that are generated on a specific date.

SUBSTR (B.CREATED_DATE, 1,7) = '22-10' extracts the first 7 digits of B.CREATED_DATE and selects only the rows matching '2022-10'.

This allows you to view only posts created in October 2022.

Finally, sort the results through the ORDER BY clause.

Sort the results by R.CREATED_DATE and B.TITLE, in order of comment creation date and post title.

##### Conclusion

This query allows you to view posts written in October 2022 and comments on those posts in order of date and title.
