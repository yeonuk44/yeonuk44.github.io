---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sum_Of_String_Integers
title: 문자열 정수의 합(with.Java)
# title: Sum of String Integers (with.Java)
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
date: 2023-11-08 09:00:00 +0900
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

### "정수 부분" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

실수 flo가 매개 변수로 주어질 때, flo의 정수 부분을 return하도록 solution 함수를 완성해주세요.

##### 입출력 예시

| flo   | result |
| ----- | ------ |
| 1.42  | 1      |
| 69.32 | 69     |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(double flo) {
        int answer = (int) flo;
        return answer;
    }
}
```

##### 풀이 설명

float 값을 int 값으로 변환하려면 명시적 형변환(Explicit Casting)을 사용해야 합니다.

float 값에서 int 값으로 변환하면 소수점 이하의 값은 버려집니다. Java에서는 (int)를 사용하여 형변환을 수행합니다.

###### 참고

형변환은 데이터 손실이 발생할 수 있으므로 주의해야 합니다. 만약 소수점 이하의 값을 보존하고자 한다면, 반올림 또는 다른 방법을 사용해야 합니다.
