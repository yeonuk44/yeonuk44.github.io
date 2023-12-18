---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Addition_Of_Fractions
title: Addition of Fractions (with.Java)
# title: Addition of Fractions (with.Java)
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
date: 2023-12-18 09:00:00 +0900
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

## "두 수의 나눗셈" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

수 num1과 num2가 매개변수로 주어질 때, num1을 num2로 나눈 값에 1,000을 곱한 후 정수 부분을 return 하도록 soltuion 함수를 완성해주세요.

#### 입출력 예시

| num1 | num2 | result |
| ---- | ---- | ------ |
| 7    | 3    | 2333   |
| 3    | 2    | 1500   |
| 1    | 6    | 62     |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int num1, int num2) {
        int answer = 0;
        double result = ((double)num1 / num2) * 1000;
        answer = (int) result;
        return answer;
    }
}
```

#### 풀이 설명

int answer = 0;: 결과 값을 저장할 변수 answer를 초기화합니다.

(double)num1 / num2: 먼저 num1을 double로 형변환하고, num2로 나눠서 두 수의 비율을 계산합니다. 이렇게 하는 이유는 나눗셈 결과를 실수로 얻기 위함입니다.

- 1000: 계산된 비율에 1000을 곱하여 백분율을 천 배로 확장합니다.

(int) result: 계산된 결과를 정수로 형변환하여 answer에 저장합니다.

return answer;: 계산된 결과를 반환합니다.
