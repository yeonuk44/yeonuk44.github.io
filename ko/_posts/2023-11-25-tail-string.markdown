---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Tail_String
title: 꼬리 문자열(with.Java)
# title: Tail String (with.Java)
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
date: 2023-11-25 09:00:00 +0900
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

## "꼬리 문자열" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열들이 담긴 리스트가 주어졌을 때, 모든 문자열들을 순서대로 합친 문자열을 꼬리 문자열이라고 합니다.

꼬리 문자열을 만들 때 특정 문자열을 포함한 문자열은 제외시키려고 합니다.

예를 들어 문자열 리스트 ["abc", "def", "ghi"]가 있고 문자열 "ef"를 포함한 문자열은 제외하고 꼬리 문자열을 만들면 "abcghi"가 됩니다.

문자열 리스트 str_list와 제외하려는 문자열 ex가 주어질 때, str_list에서 ex를 포함한 문자열을 제외하고 만든 꼬리 문자열을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예시

| str_list              | ex   | result   |
| --------------------- | ---- | -------- |
| ["abc", "def", "ghi"] | "ef" | "abcghi" |
| ["abc", "bbc", "cbc"] | "c"  | ""       |

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String[] str_list, String ex) {
        String answer = "";
        for(String temp: str_list){
            answer += temp.contains(ex) ? "" : temp;
        }
        return answer;
    }
}
```

#### 풀이 설명

String answer = "";: 결과를 저장할 빈 문자열 answer를 초기화합니다.

for(String temp : str_list) : 문자열 배열 str_list를 반복하면서 각 문자열 temp를 검사합니다.

answer += temp.contains(ex) ? "" : temp;: 현재 문자열 temp가 ex를 포함하면 빈 문자열을 추가하지만, 포함하지 않으면 temp 문자열을 answer에 추가합니다.

return answer;: str_list에서 ex를 포함하지 않는 문자열들을 연결한 결과인 answer를 반환합니다.
