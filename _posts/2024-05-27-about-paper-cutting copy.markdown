---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Paper_Cutting
title: Paper Cutting (with.Java)
# title: Paper Cutting (with.Java)
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
date: 2024-05-27 09:00:00 +0900
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

## "종이 자르기 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 큰 종이를 1 x 1 크기로 자르려고 합니다.

예를 들어 2 x 2 크기의 종이를 1 x 1 크기로 자르려면 최소 가위질 세 번이 필요합니다.

정수 M, N이 매개변수로 주어질 때, M x N 크기의 종이를 최소로 가위질 해야하는 횟수를 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 0 < M, N < 100
- 종이를 겹쳐서 자를 수 없습니다.

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| M   | N   | result |
| --- | --- | ------ |
| 2   | 2   | 3      |
| 2   | 5   | 9      |
| 1   | 1   | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int M, int N) {
        int answer = (M * N) - 1;
        return answer;
    }
}
```

### 풀이 리뷰

주어진 M과 N을 이용하여 격자 모양의 영역에서 하나의 셀을 제외한 나머지 셀의 개수를 계산하는 함수입니다.

먼저, 변수 answer를 선언하고, `(M * N) - 1`로 초기화합니다.

이것은 격자의 총 셀 개수에서 하나를 제외한 값입니다.

최종적으로 answer를 반환합니다.
