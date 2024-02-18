---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Remove_Duplicate_Characters
title: Remove duplicate characters (with.Java)
# title: Remove duplicate characters (with.Java)
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
date: 2024-02-18 09:00:00 +0900
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

## "배열 원소의 길이" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 배열 strlist가 매개변수로 주어집니다.

strlist 각 원소의 길이를 담은 배열을 retrun하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ strlist 원소의 길이 ≤ 100
- strlist는 알파벳 소문자, 대문자, 특수문자로 구성되어 있습니다.

#### 입출력 예시

| strlist                        | result       |
| ------------------------------ | ------------ |
| ["We", "are", "the", "world!"] | [2, 3, 3, 6] |
| ["I", "Love", "Programmers."]  | [1, 4, 12]   |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(String[] strlist) {
        int[] answer = new int[strlist.length];
        int count = 0;
        for(String temp : strlist){
            answer[count++] = temp.length();
        }
        return answer;
    }
}
```

### 풀이 설명

- 배열 초기화: int[] answer = new int[strlist.length];를 통해 주어진 문자열 배열 strlist의 길이만큼 결과를 저장할 배열 answer를 초기화한다.
- 문자열 길이 계산: for-each문을 통해 배열 strlist를 순회하면서 각 문자열의 길이를 temp.length()로 계산하여 해당 인덱스에 있는 answer 배열에 저장한다.
- 인덱스 증가: 각 문자열의 길이를 저장한 후, count 변수를 증가시켜 다음 인덱스에 값을 저장할 수 있도록 한다.
- 결과 반환: 모든 문자열의 길이를 계산하여 배열에 저장한 후, 최종적으로 결과 배열 answer를 반환한다.

**코드 장점**

- 간결한 로직: 문자열의 길이를 계산하는 간단하면서도 효율적인 로직으로 구성되어 있다.
- 확장성: 배열의 길이에 따라 유동적으로 대응할 수 있도록 배열 초기화를 동적으로 수행하고 있어, 다양한 입력에 대응 가능하다.

**코드 단점**

- 오류 처리 부족: 현재 코드는 입력된 배열이 null인 경우 등의 예외 처리를 고려하고 있지 않다. 적절한 예외 처리를 추가하는 것이 좋다.
- 반환 값 자료형 고정: 현재 코드에서는 결과 배열을 int[]로 반환하고 있지만, 입력에 따라 다양한 자료형이 필요한 경우에는 이를 대응할 수 있는 로직이 부족하다. 입력과 반환의 다양성을 고려하여 개선할 필요가 있다.
