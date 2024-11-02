---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Outputting_List_Of_Female_Members_Born_In_March
title: Outputting a list of female members born in March (with. MySQL)
# title: Outputting a list of female members born in March (with. MySQL)
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
date: 2024-11-02 09:00:00 +0900
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

부모의 형질을 모두 보유한 대장균의 ID(ID), 대장균의 형질(GENOTYPE), 부모 대장균의 형질(PARENT_GENOTYPE)을 출력하는 SQL 문을 작성해주세요.

이때 결과는 ID에 대해 오름차순 정렬해주세요.

대장균들은 일정 주기로 분화하며, 분화를 시작한 개체를 부모 개체, 분화가 되어 나온 개체를 자식 개체라고 합니다.

다음은 실험실에서 배양한 대장균들의 정보를 담은 ECOLI_DATA 테이블입니다.

ECOLI_DATA 테이블의 구조는 다음과 같으며, ID, PARENT_ID, SIZE_OF_COLONY, DIFFERENTIATION_DATE, GENOTYPE 은 각각 대장균 개체의 ID, 부모 개체의 ID, 개체의 크기, 분화되어 나온 날짜, 개체의 형질을 나타냅니다.

#### ECOLI_DATA 테이블

| NAME           | TYPE    | NULLABLE |
| -------------- | ------- | -------- |
| ID             | INTEGER | FALSE    |
| PARENT_ID      | INTEGER | TRUE     |
| SIZE_OF_COLONY | INTEGER | FALSE    |

최초의 대장균 개체의 PARENT_ID 는 NULL 값입니다.

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
SELECT A.ID, A.GENOTYPE, B.GENOTYPE AS PARENT_GENOTYPE
FROM ECOLI_DATA A, ECOLI_DATA B
WHERE A.PARENT_ID = B.ID AND B.GENOTYPE & A.GENOTYPE = B.GENOTYPE
ORDER BY ID;
```

#### 풀이 설명

이 SQL 쿼리는 _E. coli_ 데이터에서 특정 부모-자식 관계를 가진 레코드 쌍을 조회하여 반환합니다.

쿼리는 동일한 테이블인 `ECOLI_DATA`에서 데이터를 두 번 참조하며, 주요 구성 요소는 다음과 같습니다.

먼저 `SELECT` 절에서는 조회할 열을 지정합니다.

`A.ID`는 자식 _E. coli_ 레코드의 고유 식별자, `A.GENOTYPE`은 자식 *E. coli*의 유전자형 정보를 의미하며, `B.GENOTYPE AS PARENT_GENOTYPE`은 부모 *E. coli*의 유전자형 정보를 `PARENT_GENOTYPE`이라는 별칭으로 결과에 포함시킵니다.

이를 통해 자식과 부모의 유전자형 정보를 함께 출력할 수 있습니다.

이어서 `FROM` 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

여기서는 동일한 `ECOLI_DATA` 테이블을 두 번 참조하며, 각 참조에 대해 `A`와 `B`라는 별칭을 지정합니다.

`A`는 자식 *E. coli*의 데이터를, `B`는 부모 *E. coli*의 데이터를 나타냅니다.

다음으로 `WHERE` 절에서는 부모-자식 관계와 유전자형 조건을 설정하여 필요한 데이터를 필터링합니다.

- `A.PARENT_ID = B.ID` 조건은 `A` 테이블의 `PARENT_ID` 값이 `B` 테이블의 `ID` 값과 일치하는 경우를 선택합니다. 이는 `A` 레코드가 `B` 레코드의 자식임을 의미합니다.
- `B.GENOTYPE & A.GENOTYPE = B.GENOTYPE` 조건은 부모 _E. coli_ (`B`)의 유전자형이 자식 _E. coli_ (`A`)의 유전자형의 일부인 경우를 선택합니다. 비트 AND 연산을 통해 부모의 유전자형이 자식의 유전자형에 포함되는지 확인하며, 이 조건을 만족하는 경우만 결과에 포함됩니다.

마지막으로 `ORDER BY ID` 절을 통해 결과를 정렬합니다.

자식 _E. coli_ 레코드의 `ID`를 기준으로 오름차순 정렬하여, ID 순서대로 결과를 확인할 수 있습니다.

이 쿼리를 통해 특정 부모-자식 관계를 가지며, 부모의 유전자형이 자식의 유전자형에 포함된 _E. coli_ 레코드 쌍의 ID와 유전자형 정보를 조회할 수 있습니다.

이를 통해 유전자형의 상속 패턴이나 특정 유전자형 간의 관계를 분석하는 데 유용하게 활용할 수 있습니다.
