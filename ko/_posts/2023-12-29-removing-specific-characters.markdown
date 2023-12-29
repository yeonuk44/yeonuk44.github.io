---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Removing_Specific_Characters
title: 특정 문자 제거하기(with.Java)
# title: Removing Specific Characters (with.Java)
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
date: 2023-12-29 09:00:00 +0900
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

## "특정 문자 제거하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 my_string과 문자 letter이 매개변수로 주어집니다. my_string에서 letter를 제거한 문자열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

1 ≤ my_string의 길이 ≤ 100

letter은 길이가 1인 영문자입니다.

my_string과 letter은 알파벳 대소문자로 이루어져 있습니다.

대문자와 소문자를 구분합니다.

#### 입출력 예시

| my_string | letter | result  |
| --------- | ------ | ------- |
| "abcdef"  | "f"    | "abcde" |
| "CBdbe"   | "B"    | "Cdbe"  |

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String my_string, String letter) {
        StringBuilder result = new StringBuilder();
        for(char ch : my_string.toCharArray()){
            if(ch != letter.charAt(0)){
                result.append(ch);
            }
        }
        return result.toString();
    }
}
```

#### 풀이 설명

이 코드는 문자열 my_string에서 특정 문자 letter를 제외한 문자들로 이루어진 새로운 문자열을 생성하는 함수입니다. 아래는 코드의 주요 부분에 대한 간단한 설명입니다.

주요 코드의 간단한 설명

```java
class Solution {
    public String solution(String my_string, String letter) {
        // StringBuilder 객체를 생성하여 결과 문자열을 누적
        StringBuilder result = new StringBuilder();

        // 문자열 my_string을 문자 배열로 변환하고 각 문자에 대해 반복
        for (char ch : my_string.toCharArray()) {
            // 현재 문자가 제외할 문자 letter와 같지 않은 경우에만 결과에 추가
            if (ch != letter.charAt(0)) {
                result.append(ch);
            }
        }

        // 최종 결과를 문자열로 변환하여 반환
        return result.toString();
    }
}
```

해당 코드의 주요 단계:

StringBuilder 객체 result를 생성하여 최종 결과 문자열을 누적합니다.

문자열 my_string을 문자 배열로 변환하고 각 문자에 대해 반복합니다.

현재 문자가 제외할 문자 letter와 같지 않은 경우에만 result에 해당 문자를 추가합니다.

최종적으로 result를 문자열로 변환하여 반환합니다.

예를 들어, solution("hello", "l")을 호출하면 "heo"가 반환됩니다.
