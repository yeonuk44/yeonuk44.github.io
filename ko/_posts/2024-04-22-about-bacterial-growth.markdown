---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Bacterial_Growth
title: 세균 증식(with.Java)
# title: Bacterial growth (with.Java)
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
date: 2024-04-22 09:00:00 +0900
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

## "세균 증식(with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

어떤 세균은 1시간에 두배만큼 증식한다고 합니다.

처음 세균의 마리수 n과 경과한 시간 t가 매개변수로 주어질 때 t시간 후 세균의 수를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ n ≤ 10
- 1 ≤ t ≤ 15

#### 입출력 예시

<!-- | n   | result |
| --- | ------ |
| 144 | 1      |
| 976 | 2      | -->

| n   | t   | result |
| --- | --- | ------ |
| 2   | 10  | 2048   |
| 7   | 15  | 229376 |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int n, int t) {
        int answer = n;
        for(int i = 0; i < t; i++){
            answer *= 2;
        }
        return answer;
    }
}
```

### 풀이 설명

int answer = n;: answer 변수를 n으로 초기화합니다.

for(int i = 0; i < t; i++): 0부터 t-1까지 반복하는 반복문을 실행합니다.

answer에 2를 곱합니다.

return answer;: 최종적으로 answer 값을 반환합니다.

이 코드는 n을 t번 반복하여 2를 곱한 값을 반환하는 기능을 가지고 있습니다.

예를 들어, n이 2, t가 3인 경우 2를 3번 반복하여 8을 반환합니다.
