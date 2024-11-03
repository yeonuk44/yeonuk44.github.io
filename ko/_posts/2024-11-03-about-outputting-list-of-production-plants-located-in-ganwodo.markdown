---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Outputting_List_Of_Production_Plants_Located_In_Ganwondo
title: 강원도에 위치한 생산공장 목록 출력하기 (with. MySQL)
# title: Outputting a list of production plants located in Gangwon-do (with. MySQL)
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
date: 2024-11-03 09:00:00 +0900
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

## 강원도에 위치한 생산공장 목록 출력하기 (with. MySQL)

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

FOOD_FACTORY 테이블에서 강원도에 위치한 식품공장의 공장 ID, 공장 이름, 주소를 조회하는 SQL문을 작성해주세요.

이때 결과는 공장 ID를 기준으로 오름차순 정렬해주세요.

다음은 식품공장의 정보를 담은 FOOD_FACTORY 테이블입니다.

FOOD_FACTORY 테이블은 다음과 같으며 FACTORY_ID, FACTORY_NAME, ADDRESS, TLNO는 각각 공장 ID, 공장 이름, 주소, 전화번호를 의미합니다.

#### ECOLI_DATA 테이블

<!-- | NAME           | TYPE    | NULLABLE |
| -------------- | ------- | -------- |
| ID             | INTEGER | FALSE    |
| PARENT_ID      | INTEGER | TRUE     |
| SIZE_OF_COLONY | INTEGER | FALSE    | -->

<!-- #### 제한사항

- a의 길이는 1 이상 1,000,000 이하입니다.
- a[i]는 i+1 번째 풍선에 써진 숫자를 의미합니다.
- a의 모든 수는 -1,000,000,000 이상 1,000,000,000 이하인 정수입니다.
- a의 모든 수는 서로 다릅니다. -->

<!-- #### 입출력 예 -->

| Column name  | Type         | Nullable |
| ------------ | ------------ | -------- |
| FACTORY_ID   | VARCHAR(10)  | FALSE    |
| FACTORY_NAME | VARCHAR(50)  | FALSE    |
| ADDRESS      | VARCHAR(100) | FALSE    |
| TLNO         | VARCHAR(20)  | TRUE     |

<!-- | a                                     | result |
| ------------------------------------- | ------ |
| [9,-1,-5]                             | 3      |
| [-16,27,65,-2,58,-92,-71,-68,-61,-33] | 6      | -->

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### 문제 풀이

```sql
SELECT FACTORY_ID, FACTORY_NAME, ADDRESS
FROM FOOD_FACTORY
WHERE SUBSTR(ADDRESS, 1, 3) = '강원도'
ORDER BY FACTORY_ID
```

#### 풀이 설명

SUBSTR 함수를 이용해 주소에 '강원도'가 포함된 쿼리를 출력하고 ORDER BY를 통해 고공장 ID를 오름차순 기준으로 정렬했습니다.
