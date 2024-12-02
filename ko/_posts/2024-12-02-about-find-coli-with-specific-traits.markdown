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

2번 형질이 보유하지 않으면서 1번이나 3번 형질을 보유하고 있는 대장균 개체의 수(COUNT)를 출력하는 SQL 문을 작성해주세요.

1번과 3번 형질을 모두 보유하고 있는 경우도 1번이나 3번 형질을 보유하고 있는 경우에 포함합니다.

문제설명

대장균들은 일정 주기로 분화하며, 분화를 시작한 개체를 부모 개체, 분화가 되어 나온 개체를 자식 개체라고 합니다.

다음은 실험실에서 배양한 대장균들의 정보를 담은 ECOLI_DATA 테이블입니다.

ECOLI_DATA 테이블의 구조는 다음과 같으며, ID, PARENT_ID, SIZE_OF_COLONY, DIFFERENTIATION_DATE, GENOTYPE 은 각각 대장균 개체의 ID, 부모 개체의 ID, 개체의 크기, 분화되어 나온 날짜, 개체의 형질을 나타냅니다.

#### ECOLI_DATA 테이블

<!-- #### 제한사항

- a의 길이는 1 이상 1,000,000 이하입니다.
- a[i]는 i+1 번째 풍선에 써진 숫자를 의미합니다.
- a의 모든 수는 -1,000,000,000 이상 1,000,000,000 이하인 정수입니다.
- a의 모든 수는 서로 다릅니다. -->

<!-- #### 입출력 예 -->

| Column name          | Type    | Nullable |
| -------------------- | ------- | -------- |
| ID                   | INTEGER | FALSE    |
| PARENT_ID            | INTEGER | TRUE     |
| SIZE_OF_COLONY       | INTEGER | FALSE    |
| DIFFERENTIATION_DATE | DATE    | FALSE    |
| GENOTYPE             | INTEGER | FALSE    |

최초의 대장균 개체의 PARENT_ID 는 NULL 값입니다.

### 문제 풀이

```sql
SELECT COUNT(*) AS COUNT
FROM ECOLI_DATA
WHERE (GENOTYPE & 2) != 2 AND ((GENOTYPE & 1) = 1 OR (GENOTYPE & 4) = 4);
```

#### 풀이 설명

이 SQL 쿼리는 특정 조건을 만족하는 E. coli 데이터의 개수를 계산하여 반환합니다.

쿼리는 ECOLI_DATA 테이블에서 데이터를 추출하며, 주요 구성 요소는 다음과 같습니다.

먼저 SELECT 절에서는 조회할 값을 지정합니다.

COUNT(\*) AS COUNT는 조건을 만족하는 레코드의 개수를 계산하여 COUNT라는 별칭으로 결과를 출력합니다.

이 값은 조건에 부합하는 E. coli 데이터의 총 개수를 의미합니다.

이어서 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

이 경우 ECOLI_DATA 테이블이 사용됩니다.

다음으로 WHERE 절에서는 비트 연산을 사용하여 특정 조건을 설정하고, 그에 따라 데이터를 필터링합니다.

첫 번째 조건 (GENOTYPE & 2) != 2는 GENOTYPE 값이 2인 비트를 포함하지 않는 레코드를 선택합니다.

비트 연산 &는 비트 단위 AND 연산을 수행하며, GENOTYPE 값에서 2를 AND 연산한 결과가 2가 아닌 경우만 선택됩니다.

이는 GENOTYPE 값이 2의 비트 위치에 1이 설정되어 있지 않은 경우를 의미합니다.

두 번째 조건은 (GENOTYPE & 1) = 1 OR (GENOTYPE & 4) = 4입니다.

이는 GENOTYPE 값이 1이거나 4인 비트를 포함하는 레코드를 선택합니다.

(GENOTYPE & 1) = 1 조건은 GENOTYPE 값이 1의 비트 위치에 1이 설정된 경우를 의미합니다.

(GENOTYPE & 4) = 4 조건은 GENOTYPE 값이 4의 비트 위치에 1이 설정된 경우를 의미합니다.

이 두 조건 중 하나라도 만족하면 해당 레코드가 선택됩니다.

이 쿼리를 통해 비트 연산 조건을 충족하는 E. coli 데이터의 개수를 계산하여 COUNT로 반환합니다.

이를 통해 특정 유전자형 패턴을 가진 E. coli 데이터의 빈도를 분석하거나 통계적으로 파악할 수 있습니다.
