---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Truncate_And_Sort_Strings
title: 문자열 잘라서 정렬하기(with.Java)
# title:  Truncate and Sort Strings (with.Java)
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
date: 2023-10-17 09:00:00 +0900
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

### 간단한 식 계산하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 binomial이 매개변수로 주어집니다.

binomial은 "a op b" 형태의 이항식이고 a와 b는 음이 아닌 정수, op는 '+', '-', '\*' 중 하나입니다.

주어진 식을 계산한 정수를 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

binomial: "43 + 12"

result: 55

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String binomial) {
        String[] parts = binomial.split(" ");

        int a = Integer.parseInt(parts[0]);
        int b = Integer.parseInt(parts[2]);

        String op = parts[1];

        int result = 0;
        switch (op) {
            case "+":
                result = a + b;
                break;
            case "-":
                result = a - b;
                break;
            case "*":
                result = a * b;
                break;
        }

        return result;
    }
}
```

##### 풀이 설명

String[] parts = binomial.split(" ");: 주어진 binomial 문자열을 공백을 기준으로 나누어서 parts 배열에 저장합니다. 이렇게 하면 이항식의 구성 요소인 피연산자와 연산자를 분리할 수 있습니다.

int a = Integer.parseInt(parts[0]);와 int b = Integer.parseInt(parts[2]);: parts 배열의 첫 번째 요소와 세 번째 요소를 정수로 변환하여 피연산자 a와 b에 저장합니다. 이렇게 하면 이항식에서 숫자 부분을 추출합니다.

String op = parts[1];: parts 배열의 두 번째 요소를 연산자 문자열 op에 저장합니다. 이 연산자는 "+", "-", 또는 "\*" 중 하나일 것입니다.

int result = 0;: 결과 값을 저장할 변수 result를 초기화합니다.

switch (op) { ... }: op의 값을 기반으로 switch 문을 사용하여 연산을 수행합니다.

case "+": : 덧셈 연산을 수행하고 결과를 result에 저장합니다.

case "-": : 뺄셈 연산을 수행하고 결과를 result에 저장합니다.

case "\*": : 곱셈 연산을 수행하고 결과를 result에 저장합니다.

return result;: 계산된 결과를 반환합니다.
