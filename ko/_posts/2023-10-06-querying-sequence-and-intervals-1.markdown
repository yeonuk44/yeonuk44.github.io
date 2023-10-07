---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Querying_Sequences_And_Intervals_1
title: 수열과 구간 쿼리 1, 정수 배열과 이차원 정수 배열을 통해 구간 쿼리 별 값 제어 방법에 대하여(with.Java)
# title: Querying sequences and intervals 1 (with.Java)

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
date: 2023-10-06 09:00:00 +0900
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

### n보다 커질 때까지 더하기(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 numbers와 정수 n이 매개변수로 주어집니다.

numbers의 원소를 앞에서부터 하나씩 더하다가 그 합이 n보다 커지는 순간 이때까지 더했던 원소들의 합을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| numbers                  | n   | result |
| ------------------------ | --- | ------ |
| [34, 5, 71, 29, 100, 34] | 123 | 139    |
| [58, 44, 27, 10, 100]    | 139 | 239    |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] numbers, int n) {
        int answer = 0;
        for(int i = 0; i < numbers.length; i++){
            answer += numbers[i];
            if(answer > n) break;
        }
        return answer;
    }
}
```

##### 풀이 설명

int answer = 0;: 결과를 저장할 변수 answer를 초기화합니다.

for(int i = 0; i < numbers.length; i++) : 입력 배열 numbers를 반복하면서 각 요소를 검사합니다.

answer += numbers[i];: 현재 요소를 answer에 더합니다. 이렇게 하면 배열의 요소들이 순차적으로 합산됩니다.

if(answer > n) break;: 합이 n을 초과하면 반복문을 종료합니다. 즉, 합이 n을 초과하는 순간 합산을 멈춥니다.

return answer;: 최종적으로 합산된 결과 answer를 반환합니다.
