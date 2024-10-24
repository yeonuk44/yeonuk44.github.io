---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Outputting_A_List_Of_Cardiothoracic_Or_General_Surgeous
title: 흉부외과 또는 일반외과 의사 목록 출력하기 (with.MySQL)
# title: Outputting a list of cardiothoracic or general surgeons (with.MySQL)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [sql, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-24 09:00:00 +0900
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

## 흉부외과 또는 일반외과 의사 목록 출력하기 (with.MySQL) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

DOCTOR 테이블에서 진료과가 흉부외과(CS)이거나 일반외과(GS)인 의사의 이름, 의사ID, 진료과, 고용일자를 조회하는 SQL문을 작성해주세요.

이때 결과는 고용일자를 기준으로 내림차순 정렬하고, 고용일자가 같다면 이름을 기준으로 오름차순 정렬해주세요.

#### 제한사항

- 입국심사를 기다리는 사람은 1명 이상 1,000,000,000명 이하입니다.
- 각 심사관이 한 명을 심사하는데 걸리는 시간은 1분 이상 1,000,000,000분 이하입니다.
- 심사관은 1명 이상 100,000명 이하입니다.

#### 입출력 예

| Column name | Type        | Nullable |
| ----------- | ----------- | -------- |
| DR_NAME     | VARCHAR(20) | FALSE    |
| DR_ID       | VARCHAR(10) | FALSE    |
| LCNS_NO     | VARCHAR(30) | FALSE    |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### 문제 풀이

```sql
SELECT DR_NAME, DR_ID, MCDP_CD, DATE_FORMAT(HIRE_YMD, '%Y-%m-%d') AS HIRE_YMD
FROM DOCTOR
WHERE MCDP_CD = 'CS' OR MCDP_CD = 'GS' ORDER BY HIRE_YMD DESC, DR_NAME;
```

#### 풀이 설명

이 SQL 쿼리는 특정 진료과에 속한 의사들의 정보를 조회하여, 고용일을 기준으로 정렬된 결과를 반환합니다.

쿼리는 DOCTOR 테이블에서 데이터를 추출하며, 주요 구성 요소는 다음과 같습니다.

먼저 SELECT 절을 통해 조회할 열을 지정합니다.

DR_NAME은 의사의 이름, DR_ID는 의사의 고유 식별자, MCDP_CD는 진료과 코드, DATE_FORMAT(HIRE_YMD, '%Y-%m-%d') AS HIRE_YMD는 고용일을 'YYYY-MM-DD' 형식으로 변환하여 출력합니다.

이렇게 함으로써 고용일이 일관된 형식으로 나타납니다.

다음으로 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

이 경우 DOCTOR 테이블이 사용됩니다.

이어서 WHERE 절에서는 특정 조건을 설정하여 필요한 데이터를 필터링합니다.

MCDP_CD = 'CS' OR MCDP_CD = 'GS'는 진료과 코드가 'CS' (외과) 또는 'GS' (일반외과)인 의사들만 선택합니다.

이렇게 함으로써 외과와 일반외과에 속한 의사들만 조회할 수 있습니다.

마지막으로 ORDER BY 절을 통해 결과를 정렬합니다.

HIRE_YMD DESC와 DR_NAME을 기준으로 정렬하여, 고용일이 최신순으로, 동일한 고용일인 경우 이름의 오름차순으로 정렬합니다.

이를 통해 최근에 고용된 의사들부터 순서대로 정렬된 결과를 확인할 수 있습니다.

##### 결론

이 쿼리를 통해 외과와 일반외과에 속한 의사들의 이름, ID, 진료과 코드, 고용일을 최신 고용일 순으로 조회할 수 있습니다.

이 정보는 의사의 고용일과 진료과를 기반으로 한 분석에 유용합니다.
