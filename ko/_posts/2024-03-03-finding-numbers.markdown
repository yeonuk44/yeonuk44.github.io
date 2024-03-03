---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_Numbers
title: 숫자 찾기 (with.Java)
# title: Finding numbers (with.Java)
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
date: 2024-03-03 09:00:00 +0900
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

## "배열의 유사도" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

두 배열이 얼마나 유사한지 확인해보려고 합니다.

문자열 배열 s1과 s2가 주어질 때 같은 원소의 개수를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ s1, s2의 길이 ≤ 100
- 1 ≤ s1, s2의 원소의 길이 ≤ 10
- s1과 s2의 원소는 알파벳 소문자로만 이루어져 있습니다
- s1과 s2는 각각 중복된 원소를 갖지 않습니다.

#### 입출력 예시

| s1              | s2                          | result |
| --------------- | --------------------------- | ------ |
| ["a", "b", "c"] | ["com", "b", "d", "p", "c"] | 2      |
| ["n", "omg"]    | ["m", "dot"]                | 0      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String[] s1, String[] s2) {
        int answer = 0;
        for(int i = 0; i < s1.length; i++){
            for(int j = 0; j < s2.length; j++){
                answer += s1[i].equals(s2[j]) ? 1 : 0;
            }
        }
        return answer;
    }
}
```

### 풀이 설명

- 이 메서드는 두 개의 문자열 배열 s1과 s2를 인자로 받아서 실행됩니다.
- 메서드 내부에서는 answer라는 변수를 0으로 초기화하고, 이중 반복문을 사용하여 s1 배열의 각 요소와 s2 배열의 각 요소를 비교합니다.
- 두 문자열이 같다면 answer에 1을 더하고, 다르다면 0을 더합니다.
- 최종적으로 answer 변수의 값을 반환합니다.
- 이 값은 s1 배열과 s2 배열에서 같은 값이 몇 개인지를 나타냅니다.
- 예를 들어, s1 배열이 ["apple", "banana", "orange"]이고 s2 배열이 ["banana", "orange", "grape"]라면, s1 배열과 s2 배열에서 같은 값은 "banana"와 "orange"로 총 2개입니다.
- solution 메서드는 2를 반환할 것입니다.
