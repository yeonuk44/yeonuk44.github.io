---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Finding_EColi_With_Both_Parental_Traits
title: 부모의 형질을 모두 가지는 대장균 찾기(with.MySQL)
# title: Finding E. coli with both parental traits (with.MySQL)
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
date: 2024-11-01 09:00:00 +0900
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

## 부모의 형질을 모두 가지는 대장균 찾기(with.MySQL)

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

상반기 아이스크림 총주문량이 3,000보다 높으면서 아이스크림의 주 성분이 과일인 아이스크림의 맛을 총주문량이 큰 순서대로 조회하는 SQL 문을 작성해주세요.

다음은 아이스크림 가게의 상반기 주문 정보를 담은 FIRST_HALF 테이블과 아이스크림 성분에 대한 정보를 담은 ICECREAM_INFO 테이블입니다.

FIRST_HALF 테이블 구조는 다음과 같으며, SHIPMENT_ID, FLAVOR, TOTAL_ORDER 는 각각 아이스크림 공장에서 아이스크림 가게까지의 출하 번호, 아이스크림 맛, 상반기 아이스크림 총주문량을 나타냅니다.

FIRST_HALF 테이블의 기본 키는 FLAVOR입니다.

#### FIRST_HALF 테이블 구조

| NAME        | TYPE       | NULLABLE |
| ----------- | ---------- | -------- |
| SHIPMENT_ID | INT(N)     | FALSE    |
| FLAVOR      | VARCHAR(N) | FALSE    |
| TOTAL_ORDER | INT(N)     | FALSE    |

ICECREAM_INFO 테이블 구조는 다음과 같으며, FLAVOR, INGREDITENT_TYPE 은 각각 아이스크림 맛, 아이스크림의 성분 타입을 나타냅니다.

INGREDIENT_TYPE에는 아이스크림의 주 성분이 설탕이면 sugar_based라고 입력되고, 아이스크림의 주 성분이 과일이면 fruit_based라고 입력됩니다.

ICECREAM_INFO의 기본 키는 FLAVOR입니다.

ICECREAM_INFO테이블의 FLAVOR는 FIRST_HALF 테이블의 FLAVOR의 외래 키입니다.

#### ICECREAM_INFO 테이블 구조

| NAME            | TYPE       | NULLABLE |
| --------------- | ---------- | -------- |
| FLAVOR          | VARCHAR(N) | FALSE    |
| INGREDIENT_TYPE | VARCHAR(N) | FALSE    |

<!-- #### 제한사항

- a의 길이는 1 이상 1,000,000 이하입니다.
- a[i]는 i+1 번째 풍선에 써진 숫자를 의미합니다.
- a의 모든 수는 -1,000,000,000 이상 1,000,000,000 이하인 정수입니다.
- a의 모든 수는 서로 다릅니다. -->

<!-- #### 입출력 예 -->

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

### 문제 풀이

```sql
SELECT ICECREAM_INFO.FLAVOR
FROM ICECREAM_INFO, FIRST_HALF
WHERE ICECREAM_INFO.FLAVOR = FIRST_HALF.FLAVOR AND FIRST_HALF.TOTAL_ORDER > 3000 AND ICECREAM_INFO.INGREDIENT_TYPE = 'fruit_based'
ORDER BY FIRST_HALF.TOTAL_ORDER DESC;
```

#### 풀이 설명

이 SQL 쿼리는 특정 조건을 만족하는 아이스크림 맛을 조회하여 주문량 순으로 정렬된 결과를 반환합니다.

쿼리는 ICECREAM_INFO 테이블과 FIRST_HALF 테이블에서 데이터를 추출하며, 주요 구성 요소는 다음과 같습니다.

먼저 SELECT 절에서는 조회할 열을 지정합니다.

ICECREAM_INFO.FLAVOR는 아이스크림 맛을 의미하며, 이를 결과로 출력합니다.

이어서 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

ICECREAM_INFO와 FIRST_HALF 두 개의 테이블을 사용합니다.

이 두 테이블을 동시에 조회하기 위해 명시적으로 조인 조건을 지정합니다.

다음으로 WHERE 절에서는 특정 조건을 설정하여 필요한 데이터를 필터링합니다.

ICECREAM_INFO.FLAVOR = FIRST_HALF.FLAVOR는 두 테이블의 FLAVOR 열이 동일한 행을 조인하는 조건입니다.

FIRST_HALF.TOTAL_ORDER > 3000은 상반기 주문량이 3000건을 초과하는 아이스크림 맛을 선택하는 조건입니다.

ICECREAM_INFO.INGREDIENT_TYPE = 'fruit_based'는 과일 기반 재료를 사용하는 아이스크림 맛을 선택하는 조건입니다.

이 조건들을 통해 상반기 주문량이 3000건을 초과하고, 과일 기반 재료를 사용하는 아이스크림 맛만 선택할 수 있습니다.

마지막으로 ORDER BY 절을 통해 결과를 정렬합니다.

FIRST_HALF.TOTAL_ORDER DESC를 기준으로 정렬하여, 주문량이 많은 순서대로 결과를 정렬합니다.

이를 통해 주문량이 많은 아이스크림 맛부터 순서대로 결과를 확인할 수 있습니다.

##### 결론

이 쿼리를 통해 상반기 동안 주문량이 3000건을 초과하며, 과일 기반 재료를 사용하는 아이스크림 맛을 주문량 순으로 조회할 수 있습니다.

이를 통해 인기 있는 과일 기반 아이스크림 맛을 쉽게 파악할 수 있습니다.
