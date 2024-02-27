---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Characters_Appear_Only_Once
title: Characters that appear only once (with.Java)
# title: Characters that appear only once (with.Java)
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
date: 2024-02-27 09:00:00 +0900
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

## "인덱스 바꾸기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 my_string과 정수 num1, num2가 매개변수로 주어질 때, my_string에서 인덱스 num1과 인덱스 num2에 해당하는 문자를 바꾼 문자열을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 1 < my_string의 길이 < 100
- 0 ≤ num1, num2 < my_string의 길이
- my_string은 소문자로 이루어져 있습니다.
- num1 ≠ num2

#### 입출력 예시

| my_string    | num1 | num2 | result       |
| ------------ | ---- | ---- | ------------ |
| "hello"      | 1    | 2    | "hlelo"      |
| "I love you" | 3    | 6    | "I l veoyou" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String my_string, int num1, int num2) {
        char[] ch = my_string.toCharArray();

        ch[num1] = my_string.charAt(num2);
        ch[num2] = my_string.charAt(num1);

        String answer = String.valueOf(ch);
        return answer;
    }
}
```

### 풀이 설명

- 먼저 주어진 문자열을 char 배열로 변환합니다. 그리고 ch[num1] 위치의 문자를 my_string.charAt(num2)로 대체하고, ch[num2] 위치의 문자를 my_string.charAt(num1)로 대체합니다.
- 문자 교환을 마친 후, char 배열을 다시 문자열로 변환하여 answer 변수에 저장합니다. 마지막으로 answer를 반환합니다.
- 즉, solution 메서드는 주어진 문자열에서 num1과 num2 위치의 문자를 서로 교환한 결과를 반환하는 기능을 수행합니다.
