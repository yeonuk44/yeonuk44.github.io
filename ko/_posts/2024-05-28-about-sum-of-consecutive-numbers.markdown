---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sum_Of_Consecutive_Numbers
title: 연속된 수의 합 (with.Java)
# title: Sum of consecutive numbers (with.Java)
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
date: 2024-05-28 09:00:00 +0900
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

## "연속된 수의 합 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

연속된 세 개의 정수를 더해 12가 되는 경우는 3, 4, 5입니다.

두 정수 num과 total이 주어집니다.

연속된 수 num개를 더한 값이 total이 될 때, 정수 배열을 오름차순으로 담아 return하도록 solution함수를 완성해보세요.

#### 제한사항

- 1 ≤ num ≤ 100
- 0 ≤ total ≤ 1000
- num개의 연속된 수를 더하여 total이 될 수 없는 테스트 케이스는 없습니다.

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| num | total | result           |
| --- | ----- | ---------------- |
| 3   | 12    | [3, 4, 5]        |
| 5   | 15    | [1, 2, 3, 4, 5]  |
| 4   | 14    | [2, 3, 4, 5]     |
| 5   | 5     | [-1, 0, 1, 2, 3] |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int num, int total) {
        int[] answer = new int[num];
        int startNum = total / num - (num - 1) / 2;

        for(int i = 0; i < num; i++){
            answer[i] = startNum++;
        }
        return answer;
    }
}
```

### 풀이 리뷰

시작 숫자와 총 숫자의 합계가 주어졌을 때, 시작 숫자부터 시작하여 일정한 간격으로 숫자를 생성하는 함수입니다.

solution 함수는 num과 total 두 개의 매개변수를 받습니다.

먼저, 결과를 저장할 배열 answer를 생성합니다. 이 배열의 길이는 num으로 설정됩니다.

시작 숫자를 계산하기 위해 startNum 변수를 초기화합니다. 이 값은 주어진 총 숫자를 주어진 숫자로 나눈 후, 그 값에서 (숫자의 개수 - 1) / 2를 뺀 것입니다. 이렇게 함으로써 숫자를 일정한 간격으로 생성할 수 있습니다.

반복문을 사용하여 각 요소에 시작 숫자부터 시작하여 일정한 간격으로 증가하는 값을 할당합니다.
결과 배열 answer를 반환합니다.
