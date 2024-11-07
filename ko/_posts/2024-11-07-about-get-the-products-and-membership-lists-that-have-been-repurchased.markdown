---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Get_The_Products_And_Membership_Lists_That_Have_Been_Repurchased
title: 재구매가 일어난 상품과 회원 리스트 구하기 (with.MySQL)
# title: Get the products and membership lists that have been repurchased (with.MySQL)
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
date: 2024-11-07 09:00:00 +0900
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

## 재구매가 일어난 상품과 회원 리스트 구하기 (with.MySQL) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

ONLINE_SALE 테이블에서 동일한 회원이 동일한 상품을 재구매한 데이터를 구하여, 재구매한 회원 ID와 재구매한 상품 ID를 출력하는 SQL문을 작성해주세요.

결과는 회원 ID를 기준으로 오름차순 정렬해주시고 회원 ID가 같다면 상품 ID를 기준으로 내림차순 정렬해주세요.

문제설명

다음은 어느 의류 쇼핑몰의 온라인 상품 판매 정보를 담은 ONLINE_SALE 테이블 입니다.

ONLINE_SALE 테이블은 아래와 같은 구조로 되어있으며 ONLINE_SALE_ID, USER_ID, PRODUCT_ID, SALES_AMOUNT, SALES_DATE는 각각 온라인 상품 판매 ID, 회원 ID, 상품 ID, 판매량, 판매일을 나타냅니다.

#### ONLINE_SALE 테이블

<!-- #### 제한사항

- a의 길이는 1 이상 1,000,000 이하입니다.
- a[i]는 i+1 번째 풍선에 써진 숫자를 의미합니다.
- a의 모든 수는 -1,000,000,000 이상 1,000,000,000 이하인 정수입니다.
- a의 모든 수는 서로 다릅니다. -->

<!-- #### 입출력 예 -->

| Column name    | Type    | Nullable |
| -------------- | ------- | -------- |
| ONLINE_SALE_ID | INTEGER | FALSE    |
| USER_ID        | INTEGER | FALSE    |
| PRODUCT_ID     | INTEGER | FALSE    |
| SALES_AMOUNT   | INTEGER | FALSE    |
| SALES_DATE     | DATE    | FALSE    |

동일한 날짜, 회원 ID, 상품 ID 조합에 대해서는 하나의 판매 데이터만 존재합니다.

### 문제 풀이

```sql
SELECT USER_ID, PRODUCT_ID
FROM ONLINE_SALE
GROUP BY USER_ID, PRODUCT_ID
HAVING COUNT(*) >= 2
ORDER BY USER_ID, PRODUCT_ID DESC;
```

#### 풀이 설명

이 SQL 쿼리는 특정 사용자가 두 번 이상 구매한 상품의 정보를 조회하여 사용자 ID와 상품 ID 순으로 정렬된 결과를 반환합니다.

쿼리는 ONLINE_SALE 테이블에서 데이터를 추출하며, 주요 구성 요소는 다음과 같습니다.

먼저 SELECT 절에서는 조회할 열을 지정합니다.

USER_ID는 사용자의 고유 식별자, PRODUCT_ID는 상품의 고유 식별자를 의미하며, 이 두 열을 결과로 출력합니다.

이어서 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

이 경우 ONLINE_SALE 테이블이 사용됩니다.

다음으로 GROUP BY 절에서는 USER_ID와 PRODUCT_ID를 기준으로 데이터를 그룹화합니다.

이를 통해 각 사용자와 상품 조합별로 구매 기록을 그룹화할 수 있습니다.

그 후 HAVING 절에서는 그룹화된 데이터 중에서 특정 조건을 만족하는 그룹만을 선택합니다.

HAVING COUNT(\*) >= 2는 그룹 내 레코드 수가 2개 이상인 경우를 선택합니다.

이는 특정 사용자가 동일한 상품을 두 번 이상 구매한 경우를 의미합니다.

마지막으로 ORDER BY 절을 통해 결과를 정렬합니다.

USER_ID를 기준으로 오름차순 정렬하고, 동일 사용자 내에서는 PRODUCT_ID를 기준으로 내림차순 정렬합니다.

이를 통해 각 사용자가 두 번 이상 구매한 상품을 사용자 ID 순으로 정렬된 상태에서 확인할 수 있습니다.

이 쿼리를 통해 특정 사용자가 두 번 이상 구매한 상품의 사용자 ID와 상품 ID를 조회할 수 있습니다.

이를 통해 반복 구매 패턴을 분석하고, 특정 사용자와 상품 조합에 대한 인사이트를 얻을 수 있습니다.
