---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Check_Substring
title: 부분 문자열인지 확인하기(with.Java)
# title: Check if it's a substring (with.Java)
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
date: 2023-11-24 09:00:00 +0900
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

## "부분 문자열인지 확인하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

부분 문자열이란 문자열에서 연속된 일부분에 해당하는 문자열을 의미합니다.

예를 들어, 문자열 "ana", "ban", "anana", "banana", "n"는 모두 문자열 "banana"의 부분 문자열이지만, "aaa", "bnana", "wxyz"는 모두 "banana"의 부분 문자열이 아닙니다.

문자열 my_string과 target이 매개변수로 주어질 때, target이 문자열 my_string의 부분 문자열이라면 1을, 아니라면 0을 return 하는 solution 함수를 작성해 주세요.

#### 입출력 예시

| my_string | target | result |
| --------- | ------ | ------ |
| "banana"  | "ana"  | 1      |
| "banana"  | "wxyz" | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String my_string, String target) {
        int answer = 0;
        if(my_string.contains(target)){
            answer = 1;
        }
        return answer;
    }
}
```

#### 풀이 설명

문자열의 포함 여부를 확인하는 contains 메서드는 Java의 String 클래스에 내장되어 있습니다.

my_string에 부분문자열로 target이 포함되어 있으면 answer에 1을 할당하는 것으로 문자를 풀었습니다.

#### 참고

contains 메서드는 대소문자를 구분하므로 주의해야 합니다.

만약 대소문자를 무시하고 포함 여부를 확인하려면 문자열을 모두 소문자나 대문자로 변환한 후에 확인하면 됩니다.
