---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Iced_Americano
title: Iced Americano (with.Java)
# title: Iced Americano (with.Java)

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
date: 2024-02-02 09:00:00 +0900
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

## "가위, 바위, 보" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

가위는 2 바위는 0 보는 5로 표현합니다.

가위 바위 보를 내는 순서대로 나타낸 문자열 rsp가 매개변수로 주어질 때, rsp에 저장된 가위 바위 보를 모두 이기는 경우를 순서대로 나타낸 문자열을 return하도록 solution 함수를 완성해보세요.

#### 제한사항

0 < rsp의 길이 ≤ 100

rsp와 길이가 같은 문자열을 return 합니다.

rsp는 숫자 0, 2, 5로 이루어져 있습니다.

#### 입출력 예시

| rsp   | result |
| ----- | ------ |
| "2"   | "0"    |
| "205" | "052"  |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String rsp) {
        StringBuilder answer = new StringBuilder();
        for(char ch : rsp.toCharArray()){
            if(ch == '2'){
                answer.append('0');
            }else if(ch == '0'){
                answer.append('5');
            }else{
                answer.append('2');
            }
        }
        return answer.toString();
    }
}
```

### 풀이 설명

입력: rsp - 변환할 문자열.

출력: 변환된 문자열.

사용된 함수 소개: toCharArray(): 문자열을 문자 배열로 변환하는 메서드입니다.

상수 사용: 현재 코드에서 '2', '0', '5'는 상수로 사용되어 있습니다.
이러한 상수를 변수로 대체하여 유연성을 높일 수 있습니다.

입력 예외 처리: 입력이 null 또는 빈 문자열인 경우에 대한 예외 처리가 필요할 수 있습니다.

테스트 케이스 작성: 다양한 입력에 대한 테스트 케이스를 작성하여 코드의 안정성을 검증할 수 있습니다.
