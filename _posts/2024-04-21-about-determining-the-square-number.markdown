---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Determining_The_Square_Number
title: Determining the square number (with.Java)
# title: Determining the square number (with.Java)
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
date: 2024-04-21 09:00:00 +0900
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

## "문자열안에 문자열(with,Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 str1, str2가 매개변수로 주어집니다.

str1 안에 str2가 있다면 1을 없다면 2를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ str1의 길이 ≤ 100
- 1 ≤ str2의 길이 ≤ 100
- 문자열은 알파벳 대문자, 소문자, 숫자로 구성되어 있습니다.

#### 입출력 예시

<!-- | n      | result |
| ------ | ------ |
| 1234   | 10     |
| 930211 | 16     | -->

| str1                     | str2   | result |
| ------------------------ | ------ | ------ |
| "ab6CDE443fgh22iJKlmn1o" | "6CD"  | 1      |
| "ppprrrogrammers"        | "pppp" | 2      |
| "AbcAbcA"                | "AAA"  | 2      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String str1, String str2) {
        int answer = 0;
        if(str1.contains(str2)){
            answer = 1;
        }else{
            answer = 2;
        }
        return answer;
    }
}
```

### 풀이 설명

public int solution(String str1, String str2): solution이라는 이름의 메서드를 정의하고, 두 개의 문자열 str1과 str2를 매개변수로 받습니다. 정수형 값을 반환합니다.

int answer = 0;: 결과 값을 저장할 변수 answer를 0으로 초기화합니다.

if(str1.contains(str2)): 만약 str1이 str2를 포함하고 있다면,
answer = 1;: answer에 1을 대입합니다.

else: 그렇지 않으면,
answer = 2;: answer에 2를 대입합니다.

return answer;: 최종적으로 answer 값을 반환합니다.
