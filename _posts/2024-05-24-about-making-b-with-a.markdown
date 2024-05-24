---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Making_B_With_A
title: Making B with A (with.Java)
# title: Making B with A (with.Java)
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
date: 2024-05-24 09:00:00 +0900
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

## "이진수 더하기 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

이진수를 의미하는 두 개의 문자열 bin1과 bin2가 매개변수로 주어질 때, 두 이진수의 합을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- return 값은 이진수를 의미하는 문자열입니다.
- 1 ≤ bin1, bin2의 길이 ≤ 10
- bin1과 bin2는 0과 1로만 이루어져 있습니다.
- bin1과 bin2는 "0"을 제외하고 0으로 시작하지 않습니다.

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| bin1   | bin2   | result  |
| ------ | ------ | ------- |
| "10"   | "11"   | "101"   |
| "1001" | "1111" | "11000" |

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String bin1, String bin2) {
        String answer = "";
        int binarySum = Integer.parseInt(bin1,2) + Integer.parseInt(bin2,2);

        answer = Integer.toBinaryString(binarySum);

        return answer;
    }
}
```

### 풀이 리뷰

두 개의 이진수 문자열을 입력으로 받아 이를 10진수로 변환한 후 합산한 결과를 다시 이진수 문자열로 반환하는 함수입니다.

먼저 answer 변수를 빈 문자열로 초기화합니다.

Integer.parseInt() 함수를 사용하여 입력된 두 개의 이진수 문자열(bin1과 bin2)을 각각 10진수로 변환한 후 더합니다. 이렇게 하면 두 이진수의 합이 10진수로 계산됩니다.

이진수로 된 합을 다시 이진수 문자열로 변환하기 위해 Integer.toBinaryString() 함수를 사용합니다. 이 함수는 10진수를 이진수 문자열로 변환해줍니다.

변환된 이진수 문자열을 answer 변수에 할당하고 반환합니다.
