---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Outputting_List_Of_Production_Plants_Located_In_Ganwondo
title: Outputting a list of production plants located in Gangwon-do (with. MySQL)
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

## 3월에 태어난 여성 회원 목록 출력하기 (with. MySQL)

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

MEMBER_PROFILE 테이블에서 생일이 3월인 여성 회원의 ID, 이름, 성별, 생년월일을 조회하는 SQL문을 작성해주세요.

이때 전화번호가 NULL인 경우는 출력대상에서 제외시켜 주시고, 결과는 회원ID를 기준으로 오름차순 정렬해주세요.

다음은 식당 리뷰 사이트의 회원 정보를 담은 MEMBER_PROFILE 테이블입니다.

MEMBER_PROFILE 테이블은 다음과 같으며 MEMBER_ID, MEMBER_NAME, TLNO, GENDER, DATE_OF_BIRTH는 회원 ID, 회원 이름, 회원 연락처, 성별, 생년월일을 의미합니다.

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

### 문제 풀이

```sql
SELECT MEMBER_ID, MEMBER_NAME, GENDER, DATE_FORMAT(DATE_OF_BIRTH, '%Y-%m-%d') AS DATE_OF_BIRTH
FROM MEMBER_PROFILE
WHERE SUBSTR(DATE_OF_BIRTH, 6,2) = '03' AND GENDER = 'W' AND TLNO IS NOT NULL ORDER BY MEMBER_ID;
```

#### 풀이 설명

이 SQL 쿼리는 특정 조건을 만족하는 회원의 정보를 조회하여 회원 ID 순으로 정렬된 결과를 반환합니다.

쿼리는 MEMBER_PROFILE 테이블에서 데이터를 추출하며, 주요 구성 요소는 다음과 같습니다.

먼저 SELECT 절에서는 조회할 열을 지정합니다.

MEMBER_ID는 회원의 고유 식별자, MEMBER_NAME은 회원의 이름, GENDER는 성별, DATE_FORMAT(DATE_OF_BIRTH, '%Y-%m-%d') AS DATE_OF_BIRTH는 생년월일을 'YYYY-MM-DD' 형식으로 변환하여 출력합니다.

이렇게 함으로써 생년월일이 일관된 형식으로 나타납니다.

다음으로 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

이 경우 MEMBER_PROFILE 테이블이 사용됩니다.

이어서 WHERE 절에서는 특정 조건을 설정하여 필요한 데이터를 필터링합니다.

SUBSTR(DATE_OF_BIRTH, 6, 2) = '03'은 생년월일의 월 부분이 '03'(즉, 3월)인 회원만 선택합니다.

GENDER = 'W'는 성별이 여성인 회원만 선택합니다.

TLNO IS NOT NULL은 전화번호가 존재하는 회원만 선택합니다.

이 조건들을 통해 3월에 태어나고, 여성이며, 전화번호가 등록된 회원만 조회할 수 있습니다.

마지막으로 ORDER BY 절을 통해 결과를 정렬합니다.

MEMBER_ID를 기준으로 정렬하여, 회원 ID 순서대로 결과를 정렬합니다.

이를 통해 회원 ID 순으로 정렬된 결과를 확인할 수 있습니다.

##### 결론

이 쿼리를 통해 3월에 태어나고, 성별이 여성이며, 전화번호가 등록된 회원들의 ID, 이름, 성별, 생년월일을 조회할 수 있습니다.

이를 통해 특정 조건을 만족하는 회원들의 정보를 쉽게 파악할 수 있습니다.
