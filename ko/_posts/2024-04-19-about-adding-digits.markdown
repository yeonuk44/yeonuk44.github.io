---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Adding_Digits
title: 자릿수 더하기(with.Java)
# title: Adding digits (with.Java)
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
date: 2024-04-19 09:00:00 +0900
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

## "자릿수 더하기(with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 n이 매개변수로 주어질 때 n의 각 자리 숫자의 합을 return하도록 solution 함수를 완성해주세요

#### 제한사항

- 0 ≤ n ≤ 1,000,000

#### 입출력 예시

| n      | result |
| ------ | ------ |
| 1234   | 10     |
| 930211 | 16     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        String str = Integer.toString(n);
        for(int i = 0; i < str.length(); i++){
            int k = (int)str.charAt(i) - '0';
            answer += k;
        }
        return answer;
    }
}
```

### 풀이 설명

메소드 시그니처: public int solution(int n)
정수 n을 매개변수로 받고, 정수 값을 반환하는 메소드입니다.

변수 초기화: int answer = 0;
결과 값을 저장할 변수인 answer를 0으로 초기화합니다.

정수를 문자열로 변환: String str = Integer.toString(n);
입력받은 정수 n을 문자열로 변환하여 str에 저장합니다.

문자열을 순회하며 각 자리의 숫자를 더함:
for(int i = 0; i < str.length(); i++)
문자열의 길이만큼 반복합니다.

int k = (int)str.charAt(i) - '0';
문자열에서 i번째 문자를 가져와서 ASCII 코드 값을 구하고, '0'의 ASCII 코드 값을 뺀 결과를 정수로 변환하여 k에 저장합니다.

answer += k;
k 값을 answer에 더합니다.

결과 값 반환: return answer;
answer 변수에 저장된 값을 반환합니다.

이렇게 코드는 주어진 정수의 각 자리 숫자를 더한 값을 반환하는 기능을 수행합니다.
