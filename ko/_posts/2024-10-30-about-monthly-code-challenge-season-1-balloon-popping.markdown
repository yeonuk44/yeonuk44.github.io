---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Monthly_Code_Challenge_Season_1_Balloon_Popping
title: 월간 코드 챌린지 시즌1 문제, 풍선 터트리기 (with.Java)
# title: Monthly Code Challenge Season 1 questions, balloon popping (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-30 09:00:00 +0900
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

## 월간 코드 챌린지 시즌1 문제, 풍선 터트리기 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

CAR_RENTAL_COMPANY_CAR 테이블에서 자동차 종류가 'SUV'인 자동차들의 평균 일일 대여 요금을 출력하는 SQL문을 작성해주세요.

이때 평균 일일 대여 요금은 소수 첫 번째 자리에서 반올림하고, 컬럼명은 AVERAGE_FEE 로 지정해주세요.

다음은 어느 자동차 대여 회사에서 대여중인 자동차들의 정보를 담은 CAR_RENTAL_COMPANY_CAR 테이블입니다.

CAR_RENTAL_COMPANY_CAR 테이블은 아래와 같은 구조로 되어있으며, CAR_ID, CAR_TYPE, DAILY_FEE, OPTIONS 는 각각 자동차 ID, 자동차 종류, 일일 대여 요금(원), 자동차 옵션 리스트를 나타냅니다.

자동차 종류는 '세단', 'SUV', '승합차', '트럭', '리무진' 이 있습니다. 자동차 옵션 리스트는 콤마(',')로 구분된 키워드 리스트(예: '열선시트', '스마트키', '주차감지센서')로 되어있으며, 키워드 종류는 '주차감지센서', '스마트키', '네비게이션', '통풍시트', '열선시트', '후방카메라', '가죽시트' 가 있습니다.

#### 입출력 예

| Column name | Type         | Nullable |
| ----------- | ------------ | -------- |
| CAR_ID      | INTEGER      | FALSE    |
| CAR_TYPE    | VARCHAR(255) | FALSE    |
| DAILY_FEE   | INTEGER      | FALSE    |
| OPTIONS     | VARCHAR(255) | FALSE    |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### 문제 풀이

```sql
SELECT ROUND(AVG(DAILY_FEE)) AS AVERAGE_FEE
FROM CAR_RENTAL_COMPANY_CAR
GROUP BY CAR_TYPE HAVING CAR_TYPE = 'SUV'
```

#### 풀이 설명

이 SQL 쿼리는 특정 유형의 자동차에 대한 일일 대여 요금의 평균을 계산하여 반환합니다.

쿼리는 CAR_RENTAL_COMPANY_CAR 테이블에서 데이터를 추출하며, 주요 구성 요소는 다음과 같습니다.

먼저 SELECT 절에서는 계산된 평균 일일 요금을 반올림하여 AVERAGE_FEE라는 별칭으로 출력합니다.

ROUND(AVG(DAILY_FEE)) AS AVERAGE_FEE는 DAILY_FEE 열의 평균 값을 구한 후 소수점 이하를 반올림하여 정수 형태로 반환합니다.

이어서 FROM 절에서는 쿼리를 실행할 기본 테이블을 지정합니다.

이 경우 CAR_RENTAL_COMPANY_CAR 테이블이 사용됩니다.

다음으로 GROUP BY 절에서는 CAR_TYPE 열을 기준으로 데이터를 그룹화합니다.

각 자동차 유형별로 일일 대여 요금의 평균을 계산할 수 있도록 합니다.

마지막으로 HAVING 절에서는 그룹화된 데이터 중에서 특정 조건을 만족하는 그룹만을 선택합니다.

HAVING CAR_TYPE = 'SUV'는 자동차 유형이 'SUV'인 그룹만 선택합니다.

이 조건을 통해 SUV 차량에 대한 평균 일일 요금만을 계산하여 반환할 수 있습니다.

###### 결론

이 쿼리를 통해 SUV 유형의 자동차에 대한 평균 일일 대여 요금을 반올림한 값을 조회할 수 있습니다.

이를 통해 SUV 차량의 대여 요금에 대한 인사이트를 얻을 수 있습니다.
