---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Total_Number_Of_Fish_Caught
title: 특정 물고기를 잡은 총 수 구하기 (with.MySQL)
# title: Total number of fish caught (with.MySQL)
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
date: 2024-11-28 09:00:00 +0900
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

## 특정 물고기를 잡은 총 수 구하기 (with.MySQL) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

FISH_INFO 테이블에서 가장 큰 물고기 10마리의 ID와 길이를 출력하는 SQL 문을 작성해주세요.

결과는 길이를 기준으로 내림차순 정렬하고, 길이가 같다면 물고기의 ID에 대해 오름차순 정렬해주세요.

단, 가장 큰 물고기 10마리 중 길이가 10cm 이하인 경우는 없습니다.

ID 컬럼명은 ID, 길이 컬럼명은 LENGTH로 해주세요.

문제설명

낚시앱에서 사용하는 FISH_INFO 테이블은 잡은 물고기들의 정보를 담고 있습니다.

FISH_INFO 테이블의 구조는 다음과 같으며 ID, FISH_TYPE, LENGTH, TIME은 각각 잡은 물고기의 ID, 물고기의 종류(숫자), 잡은 물고기의 길이(cm), 물고기를 잡은 날짜를 나타냅니다.

#### FISH_INFO 테이블

<!-- #### 제한사항

- a의 길이는 1 이상 1,000,000 이하입니다.
- a[i]는 i+1 번째 풍선에 써진 숫자를 의미합니다.
- a의 모든 수는 -1,000,000,000 이상 1,000,000,000 이하인 정수입니다.
- a의 모든 수는 서로 다릅니다. -->

<!-- #### 입출력 예 -->

| Column name | Type    | Nullable |
| ----------- | ------- | -------- |
| ID          | INTEGER | FALSE    |
| FISH_TYPE   | INTEGER | FALSE    |
| LENGTH      | FLOAT   | TRUE     |
| TIME        | DATE    | FALSE    |

단, 잡은 물고기의 길이가 10cm 이하일 경우에는 LENGTH 가 NULL 이며, LENGTH 에 NULL 만 있는 경우는 없습니다.

### 문제 풀이

```sql
SELECT ID, LENGTH
FROM FISH_INFO
ORDER BY LENGTH DESC, ID
LIMIT 10;
```

#### 풀이 설명

이 SQL 쿼리는 물고기의 길이 정보를 기준으로 상위 10마리의 데이터를 조회하여 반환합니다.

쿼리는 FISH_INFO 테이블에서 데이터를 추출하며, 주요 구성 요소는 다음과 같습니다.

먼저 SELECT 절에서는 조회할 열을 지정합니다.

ID는 물고기의 고유 식별자, LENGTH는 물고기의 길이를 의미하며, 이 두 열을 결과로 출력합니다.

이어서 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

이 경우 FISH_INFO 테이블이 사용됩니다.

다음으로 ORDER BY 절을 통해 결과를 정렬합니다.

정렬 기준은 두 가지로, 첫 번째는 LENGTH DESC입니다.

이는 물고기의 길이를 기준으로 내림차순 정렬하여 가장 큰 물고기부터 순서대로 정렬합니다.

두 번째 정렬 기준은 ID로, 길이가 동일한 경우에는 ID를 기준으로 오름차순 정렬합니다.

이를 통해 같은 길이를 가진 물고기들이 고유 ID 순서대로 정렬됩니다.

마지막으로 LIMIT 10은 쿼리 결과에서 상위 10개의 행만 선택하여 반환합니다.

이는 정렬된 결과 중에서 가장 큰 10마리의 물고기 정보를 반환하는 역할을 합니다.

이 쿼리를 통해 가장 큰 물고기 10마리의 ID와 길이를 조회할 수 있습니다.

이를 통해 특정 크기 이상의 물고기를 분석하거나, 크기 기준으로 상위 물고기들을 쉽게 파악할 수 있습니다.
