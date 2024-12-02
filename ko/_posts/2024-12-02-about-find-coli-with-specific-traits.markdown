---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Find_Coli_With_Specific_Traits
title: 특정 형질을 가지는 대장균 찾기(with.MySQL)
# title: Find E. coli with specific traits (with.MySQL)
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
date: 2024-12-02 09:00:00 +0900
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

## 특정 형질을 가지는 대장균 찾기(with.MySQL) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

FISH_INFO 테이블에서 잡은 BASS와 SNAPPER의 수를 출력하는 SQL 문을 작성해주세요.

컬럼명은 'FISH_COUNT`로 해주세요.

문제설명

낚시앱에서 사용하는 FISH_INFO 테이블은 잡은 물고기들의 정보를 담고 있습니다.

FISH_INFO 테이블의 구조는 다음과 같으며 ID, FISH_TYPE, LENGTH, TIME은 각각 잡은 물고기의 ID, 물고기의 종류(숫자), 잡은 물고기의 길이(cm), 물고기를 잡은 날짜를 나타냅니다.

FISH_NAME_INFO 테이블은 물고기의 이름에 대한 정보를 담고 있습니다.

FISH_NAME_INFO 테이블의 구조는 다음과 같으며, FISH_TYPE, FISH_NAME 은 각각 물고기의 종류(숫자), 물고기의 이름(문자) 입니다.

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

| Column name | Type    | Nullable |
| ----------- | ------- | -------- |
| FISH_TYPE   | INTEGER | FALSE    |
| FISH_NAME   | VARCHAR | FALSE    |

### 문제 풀이

```sql
SELECT COUNT(FN.FISH_TYPE) AS FISH_COUNT
FROM FISH_INFO AS FI JOIN FISH_NAME_INFO AS FN ON FI.FISH_TYPE = FN.FISH_TYPE
WHERE FISH_NAME LIKE 'BASS' OR FISH_NAME LIKE 'SNAPPER';
```

#### 풀이 설명

이 SQL 쿼리는 특정 종류의 물고기(BASS 또는 SNAPPER)의 개수를 계산하여 반환합니다.

쿼리는 FISH_INFO 테이블과 FISH_NAME_INFO 테이블을 조인하여 데이터를 추출하며, 주요 구성 요소는 다음과 같습니다.

먼저 SELECT 절에서는 조회할 값을 지정합니다.

COUNT(FN.FISH_TYPE) AS FISH_COUNT는 조건을 만족하는 물고기의 종류를 세어, 그 개수를 FISH_COUNT라는 별칭으로 출력합니다.

이는 BASS 또는 SNAPPER에 해당하는 물고기의 총 수를 의미합니다.

이어서 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

여기서는 FISH_INFO 테이블을 사용하며, 이를 FI라는 별칭으로 지정합니다.

다음으로 JOIN 절을 사용하여 FISH_NAME_INFO 테이블과 FISH_INFO 테이블을 조인합니다.

조인의 조건은 FI.FISH_TYPE = FN.FISH_TYPE으로, 두 테이블의 FISH_TYPE 열을 기준으로 연결됩니다.

이렇게 함으로써 물고기 정보와 물고기 이름 정보를 결합하여 조회할 수 있습니다.

WHERE 절에서는 특정 조건을 설정하여 필요한 데이터를 필터링합니다.

FISH_NAME LIKE 'BASS' OR FISH_NAME LIKE 'SNAPPER' 조건은 물고기 이름이 'BASS' 또는 'SNAPPER'인 경우를 선택합니다.

이 조건에 따라 BASS와 SNAPPER라는 이름을 가진 물고기만 선택됩니다.

이 쿼리를 통해 BASS 또는 SNAPPER로 이름이 지정된 물고기의 총 수를 계산하여 FISH_COUNT로 반환할 수 있습니다.

이를 통해 특정 종류의 물고기 개체 수를 쉽게 파악할 수 있으며, 특정 어종에 대한 분석이나 통계에 유용하게 활용될 수 있습니다.
