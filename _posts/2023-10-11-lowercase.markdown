---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Lowercase
title: Lowercase (with.Java)
# title: Lowercase (with.Java)
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
date: 2023-10-11 09:00:00 +0900
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

### 원하는 문자열 찾기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

알파벳으로 이루어진 문자열 myString과 pat이 주어집니다.

myString의 연속된 부분 문자열 중 pat이 존재하면 1을 그렇지 않으면 0을 return 하는 solution 함수를 완성해 주세요.

단, 알파벳 대문자와 소문자는 구분하지 않습니다.

##### 입출력 예시

| myString  | pat     | return |
| --------- | ------- | ------ |
| "AbCdEfG" | "aBc"   | 1      |
| "aaAA"    | "aaaaa" | 0      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String myString, String pat) {
        int answer = 0;
        String lowerStr = myString.toLowerCase();
        String lowerPat = pat.toLowerCase();
        if(lowerStr.contains(lowerPat)){
            answer = 1;
        }
        return answer;
    }
}
```

##### 풀이 설명

int answer = 0;: 결과를 저장할 변수 answer를 초기화합니다. 초기값은 0입니다.

String lowerStr = myString.toLowerCase();: 입력 문자열 myString을 소문자로 변환하여 lowerStr에 저장합니다. 이렇게 하는 이유는 대소문자 구분 없이 판단하기 위함입니다.

String lowerPat = pat.toLowerCase();: 입력 문자열 pat도 소문자로 변환하여 lowerPat에 저장합니다.

if(lowerStr.contains(lowerPat)) : lowerStr 문자열에 lowerPat 문자열이 포함되어 있는 경우:

answer를 1로 설정합니다.

return answer;: 결과를 나타내는 answer를 반환합니다.

만약 lowerStr에 lowerPat이 포함되어 있으면 1, 그렇지 않으면 0을 반환합니다.
