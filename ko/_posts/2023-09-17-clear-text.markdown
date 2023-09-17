---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Clear_Text
title: 글자 지우기, 배열에 존재하는 값에 해당하는 인덱스를 문자열에서 지우는 방법에 대하여(with.Java)
# title: Clearing characters, how to clear the index corresponding to a value present in an array from a string (with.Java)

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
date: 2023-09-17 09:00:00 +0900
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

### qr code(with.Java)에 대한 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

두 정수 q, r과 문자열 code가 주어질 때, code의 각 인덱스를 q로 나누었을 때 나머지가 r인 위치의 문자를 앞에서부터 순서대로 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| q   | r   | code               | result        |
| --- | --- | ------------------ | ------------- |
| 3   | 1   | "qjnwezgrpirldywt" | "jerry"       |
| 1   | 0   | "programmers"      | "programmers" |

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(int q, int r, String code) {
        StringBuilder sb = new StringBuilder();
        for(int i = 0; i < code.length(); i++){
            if(i % q == r) sb.append(code.charAt(i));
        }
        return sb.toString();
    }
}
```

##### 풀이 설명

StringBuilder sb = new StringBuilder();: 새로운 문자열을 빌드하기 위한 StringBuilder 객체 sb를 생성합니다.

for(int i = 0; i < code.length(); i++) {: 문자열 code를 반복하면서 각 문자를 검사합니다.

if(i % q == r) sb.append(code.charAt(i));: 현재 인덱스 i를 q로 나눈 나머지가 r과 같다면, 현재 인덱스의 문자를 sb에 추가합니다.

return sb.toString();: 최종적으로 sb에 저장된 문자들을 문자열로 변환하고 반환합니다.

이 코드는 입력 문자열 code에서 q로 나눈 나머지가 r과 같은 위치에 있는 문자들을 선택하여 새로운 문자열을 생성합니다. 예를 들어, q가 3이고 r이 1이면, 문자열의 인덱스가 1, 4, 7, 10, ... 등 3의 배수에서 문자를 선택하여 새로운 문자열을 생성합니다.
