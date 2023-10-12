---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Lowercase
title: 소문자로 바꾸기(with.Java)
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

### 소문자로 바꾸기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

알파벳으로 이루어진 문자열 myString이 주어집니다.

모든 알파벳을 소문자로 변환하여 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| myString  | return    |
| --------- | --------- |
| "aBcDeFg" | "abcdefg" |
| "aaa"     | "aaa"     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String myString) {
        return myString.toLowerCase();
    }
}
```

##### 풀이 설명

String solution(String myString) : 문자열을 입력으로 받는 함수를 정의합니다.

return myString.toLowerCase();: myString 문자열을 소문자로 변환한 결과를 반환합니다.

이 코드는 입력 문자열에 포함된 모든 문자를 소문자로 변환하고 그 결과를 반환합니다. 대소문자를 구분하지 않아야 하는 경우에 유용하게 사용될 수 있습니다.
