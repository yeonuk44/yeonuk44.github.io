---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Changing_Index
title: Changing index (with.Java)
# title: Changing index (with.Java)
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
date: 2024-02-26 09:00:00 +0900
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

## "약수 구하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 n이 매개변수로 주어질 때, n의 약수를 오름차순으로 담은 배열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ n ≤ 10,000

#### 입출력 예시

| n   | result                     |
| --- | -------------------------- |
| 24  | [1, 2, 3, 4, 6, 8, 12, 24] |
| 29  | [1, 29]                    |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int n) {
        int cnt = 0;
        for(int i = 1; i <= n; i++){
            if(n % i == 0){
                cnt++;
            }
        }
        int[] answer = new int[cnt];
        int idx = 0;
        for(int i = 1; i <= n; i++){
            if(n % i == 0){
                answer[idx++] = i;
            }
        }
        return answer;
    }
}
```

### 풀이 설명

- cnt 변수를 선언하고 0으로 초기화합니다. 이 변수는 약수의 개수를 세기 위해 사용됩니다.
- 1부터 n까지 반복하는 for문을 실행합니다. 변수 i는 1부터 n까지의 값을 가집니다. 만약 n을 i로 나눈 나머지가 0이라면, 즉 i가 n의 약수라면,
  cnt 값을 1 증가시킵니다.
- cnt 길이의 배열 answer를 선언합니다.
- idx 변수를 선언하고 0으로 초기화합니다. 이 변수는 answer 배열의 인덱스를 가리킵니다.
- 1부터 n까지 반복하는 for문을 실행합니다. 변수 i는 1부터 n까지의 값을 가집니다. 만약 n을 i로 나눈 나머지가 0이라면, 즉 i가 n의 약수라면,
- answer 배열의 idx 인덱스에 i 값을 할당하고, idx 값을 1 증가시킵니다.
- answer 배열을 반환합니다.
