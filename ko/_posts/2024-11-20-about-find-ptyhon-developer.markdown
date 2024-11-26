---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Find_Python_Developer
title: Python 개발자 찾기 (with.MySQL)
# title: Find Python Developer (with.MySQL)
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
date: 2024-11-20 09:00:00 +0900
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

## Python 개발자 찾기 (with.MySQL) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

DEVELOPER_INFOS 테이블에서 Python 스킬을 가진 개발자의 정보를 조회하려 합니다.

Python 스킬을 가진 개발자의 ID, 이메일, 이름, 성을 조회하는 SQL 문을 작성해 주세요.

결과는 ID를 기준으로 오름차순 정렬해 주세요.

문제설명

DEVELOPER_INFOS 테이블은 개발자들의 프로그래밍 스킬 정보를 담은 테이블입니다.

DEVELOPER_INFOS 테이블 구조는 다음과 같으며, ID, FIRST_NAME, LAST_NAME, EMAIL, SKILL_1, SKILL_2, SKILL_3는 각각 ID, 이름, 성, 이메일, 첫 번째 스킬, 두 번째 스킬, 세 번째 스킬을 의미합니다.

#### DEVELOPER_INFOS 테이블

<!-- #### 제한사항

- a의 길이는 1 이상 1,000,000 이하입니다.
- a[i]는 i+1 번째 풍선에 써진 숫자를 의미합니다.
- a의 모든 수는 -1,000,000,000 이상 1,000,000,000 이하인 정수입니다.
- a의 모든 수는 서로 다릅니다. -->

<!-- #### 입출력 예 -->

| NAME       | TYPE       | UNIQUE | NULLABLE |
| ---------- | ---------- | ------ | -------- |
| ID         | VARCHAR(N) | Y      | N        |
| FIRST_NAME | VARCHAR(N) | N      | Y        |
| LAST_NAME  | VARCHAR(N) | N      | Y        |
| EMAIL      | VARCHAR(N) | Y      | N        |
| SKILL_1    | VARCHAR(N) | N      | Y        |
| SKILL_2    | VARCHAR(N) | N      | Y        |
| SKILL_3    | VARCHAR(N) | N      | Y        |

### 문제 풀이

```sql
SELECT ID, EMAIL, FIRST_NAME, LAST_NAME
FROM DEVELOPER_INFOS
WHERE "Python" IN (SKILL_1, SKILL_2, SKILL_3)
ORDER BY ID;
```

#### 풀이 설명

이 SQL 쿼리는 특정 기술을 보유한 개발자들의 정보를 조회하여 개발자 ID 순으로 정렬된 결과를 반환합니다.

쿼리는 DEVELOPER_INFOS 테이블에서 데이터를 추출하며, 주요 구성 요소는 다음과 같습니다.

먼저 SELECT 절에서는 조회할 열을 지정합니다.

ID는 개발자의 고유 식별자, EMAIL은 개발자의 이메일 주소, FIRST_NAME과 LAST_NAME은 각각 개발자의 이름과 성을 의미하며, 이 네 가지 정보를 결과로 출력합니다.

이어서 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

이 경우 DEVELOPER_INFOS 테이블이 사용됩니다.

다음으로 WHERE 절에서는 특정 조건을 설정하여 필요한 데이터를 필터링합니다.

"Python" IN (SKILL_1, SKILL_2, SKILL_3)은 개발자가 보유한 세 가지 기술 중 하나라도 'Python'이 포함되어 있는 경우를 선택합니다.

이를 통해 Python 기술을 보유한 개발자들만 조회할 수 있습니다.

마지막으로 ORDER BY 절을 통해 결과를 정렬합니다.

ID를 기준으로 오름차순 정렬하여, 개발자 ID 순서대로 결과를 확인할 수 있습니다.

이 쿼리를 통해 Python 기술을 보유한 개발자들의 ID, 이메일, 이름, 성을 조회할 수 있습니다.

이를 통해 특정 기술을 보유한 개발자들의 정보를 쉽게 파악할 수 있으며, 기술 역량에 따른 분석이나 채용 과정에 유용하게 활용할 수 있습니다.
