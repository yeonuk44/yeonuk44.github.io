---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Binary_Addition
title: 이진수 더하기 (with.Java)
# title: Binary addition (with.Java)
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
date: 2024-05-23 09:00:00 +0900
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

## "치킨 쿠폰 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

프로그래머스 치킨은 치킨을 시켜먹으면 한 마리당 쿠폰을 한 장 발급합니다.

쿠폰을 열 장 모으면 치킨을 한 마리 서비스로 받을 수 있고, 서비스 치킨에도 쿠폰이 발급됩니다.

시켜먹은 치킨의 수 chicken이 매개변수로 주어질 때 받을 수 있는 최대 서비스 치킨의 수를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- chicken은 정수입니다.
- 0 ≤ chicken ≤ 1,000,000

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| chicken | result |
| ------- | ------ |
| 100     | 11     |
| 1,081   | 120    |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int chicken) {
        int answer = 0;

        while (chicken >= 10) {
            answer += chicken / 10;
            chicken = chicken / 10 + chicken % 10;
        }
        return answer;
    }
}
```

### 풀이 리뷰

먼저 answer 변수를 0으로 초기화합니다.

while 루프를 사용하여 치킨의 개수가 10 이상인 경우에만 반복합니다.

현재 치킨의 개수에서 10을 나눈 몫을 answer에 더합니다. 이는 현재 치킨의 개수에서 얻을 수 있는 쿠폰의 개수입니다.

치킨의 개수를 10으로 나눈 몫에 치킨의 개수를 10으로 나눈 나머지를 더하여 다음 치킨의 개수를 업데이트합니다.

이렇게 함으로써 한 번에 구매한 치킨의 개수와 쿠폰으로 받은 치킨의 개수를 합산하여 다음 단계의 치킨 개수를 계산합니다.

while 루프가 종료되면 치킨의 개수가 10 미만이 되었으므로 함수는 마지막으로 계산된 answer 값을 반환합니다.
