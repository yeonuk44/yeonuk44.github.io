---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Choosing_A_Multiple_Of_N
title: n의 배수 고르기 (with.Java)
# title: Choosing a multiple of n (with.Java)
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
date: 2024-03-04 09:00:00 +0900
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

## "n의 배수 고르기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 n과 정수 배열 numlist가 매개변수로 주어질 때, numlist에서 n의 배수가 아닌 수들을 제거한 배열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ n ≤ 10,000
- 1 ≤ numlist의 크기 ≤ 100
- 1 ≤ numlist의 원소 ≤ 100,000

#### 입출력 예시

| n   | numlist                        | result             |
| --- | ------------------------------ | ------------------ |
| 3   | [4, 5, 6, 7, 8, 9, 10, 11, 12] | [6, 9, 12]         |
| 5   | [1, 9, 3, 10, 13, 5]           | [10, 5]            |
| 12  | [2, 100, 120, 600, 12, 12]     | [120, 600, 12, 12] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int n, int[] numlist) {
        int cnt = 0;
        for(int x : numlist){
            if(x % n == 0){
                cnt++;
            }
        }
        int[] answer = new int[cnt];
        int idx = 0;
        for(int i = 0; i < numlist.length; i++){
            if(numlist[i] % n == 0){
                answer[idx++] = numlist[i];
            }
        }
        return answer;
    }
}
```

### 풀이 설명

- cnt: n으로 나누어 떨어지는 숫자의 개수를 세기 위한 변수입니다. 초기값은 0으로 설정됩니다.
- for-each 반복문: numlist 배열에서 x를 하나씩 꺼내어 반복합니다.
- x를 n으로 나누었을 때 나머지가 0이면, 즉 x가 n으로 나누어 떨어지면 cnt를 증가시킵니다.
- 결과 배열(answer) 초기화: cnt를 이용하여 결과 배열 answer의 크기를 지정합니다.
- 인덱스 변수(idx) 초기화: 결과 배열 answer에 값을 저장하기 위한 인덱스 변수 idx를 0으로 초기화합니다.
- for 반복문: numlist 배열을 인덱스 i를 이용하여 반복합니다.
- numlist[i]를 n으로 나누었을 때 나머지가 0이면, 즉 numlist[i]가 n으로 나누어 떨어지면 answer[idx]에 numlist[i]를 저장하고 idx를 1 증가시킵니다.
