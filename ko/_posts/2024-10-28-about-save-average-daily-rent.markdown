---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Save_Average_Daily_Rent
title: 평균 일일 대여 요금 구하기 (with.MySQL)
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

## 평균 일일 대여 요금 구하기 (with.MySQL) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

USED_GOODS_BOARD와 USED_GOODS_REPLY 테이블에서 2022년 10월에 작성된 게시글 제목, 게시글 ID, 댓글 ID, 댓글 작성자 ID, 댓글 내용, 댓글 작성일을 조회하는 SQL문을 작성해주세요.

결과는 댓글 작성일을 기준으로 오름차순 정렬해주시고, 댓글 작성일이 같다면 게시글 제목을 기준으로 오름차순 정렬해주세요.
0

#### 입출력 예

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

### 문제 풀이

```sql
SELECT B.TITLE, B.BOARD_ID, R.REPLY_ID, R.WRITER_ID, R.CONTENTS, DATE_FORMAT(R.CREATED_DATE, '%Y-%m-%d') AS CREATED_DATE
FROM USED_GOODS_BOARD AS B
JOIN USED_GOODS_REPLY AS R ON B.BOARD_ID = R.BOARD_ID
WHERE SUBSTR(B.CREATED_DATE, 1, 7) = '2022-10' ORDER BY R.CREATED_DATE, B.TITLE
```

#### 풀이 설명

이 SQL 쿼리는 특정 날짜에 생성된 중고 상품 게시판의 게시글과 해당 게시글에 달린 댓글을 조회하는 작업을 수행합니다.

이 쿼리는 두 개의 테이블인 USED_GOODS_BOARD와 USED_GOODS_REPLY를 조인하여 결과를 출력합니다.

다음은 쿼리의 각 부분을 자세히 설명한 내용입니다.

먼저 SELECT 절에서는 우리가 조회하고자 하는 열을 지정합니다.

B.TITLE은 게시글의 제목을, B.BOARD_ID는 게시글의 고유 식별자를, R.REPLY_ID는 댓글의 고유 식별자를, R.WRITER_ID는 댓글 작성자의 ID를, R.CONTENTS는 댓글의 내용을, 그리고 DATE_FORMAT(R.CREATED_DATE, '%Y-%m-%d') AS CREATED_DATE는 댓글 작성 날짜를 'YYYY-MM-DD' 형식으로 변환하여 출력합니다.

이어서 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

이 경우에는 USED_GOODS_BOARD 테이블을 기본 테이블로 설정합니다.

다음으로 JOIN 절을 통해 USED_GOODS_REPLY 테이블과 USED_GOODS_BOARD 테이블을 조인합니다.

조인의 조건은 ON B.BOARD_ID = R.BOARD_ID로, 두 테이블의 BOARD_ID 열을 기준으로 합니다.

이를 통해 각 게시글에 달린 댓글들을 연결할 수 있습니다.

WHERE 절에서는 조건을 지정하여 특정 날짜에 생성된 게시글만을 조회합니다.

SUBSTR(B.CREATED_DATE, 1, 7) = '2022-10'은 B.CREATED_DATE의 첫 7자리를 추출하여 '2022-10'과 일치하는 행만 선택합니다.

이를 통해 2022년 10월에 생성된 게시글만 조회할 수 있습니다.

마지막으로 ORDER BY 절을 통해 결과를 정렬합니다.

R.CREATED_DATE와 B.TITLE을 기준으로 정렬하여, 댓글 작성 날짜와 게시글 제목 순으로 결과를 정렬합니다.

##### 결론

이 쿼리를 통해 2022년 10월에 작성된 게시글과 해당 게시글에 달린 댓글을 날짜와 제목 순으로 정렬하여 확인할 수 있습니다.
