---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Calculate_Simple_Expression
title: 간단한 식 계산하기(with.Java)
# title: Calculate a simple expression (with.Java)
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
date: 2023-10-16 09:00:00 +0900
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

### "ad" 제거하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 배열 strArr가 주어집니다.

배열 내의 문자열 중 "ad"라는 부분 문자열을 포함하고 있는 모든 문자열을 제거하고 남은 문자열을 순서를 유지하여 배열로 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| strArr                        | result                        |
| ----------------------------- | ----------------------------- |
| ["and","notad","abcd"]        | ["and","abcd"]                |
| ["there","are","no","a","ds"] | ["there","are","no","a","ds"] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String[] solution(String[] strArr) {
        int count = 0;
        String ad = "ad";
        for (int i = 0; i < strArr.length; i++) {
            if (!strArr[i].contains(ad)) {
                count++;
            }
        }
        String[] answer = new String[count];
        int index = 0;
        for (int i = 0; i < strArr.length; i++) {
            if (!strArr[i].contains(ad)) {
                answer[index++] = strArr[i];
            }
        }

        return answer;
    }
}
```

##### 풀이 설명

public String[] solution(String[] strArr): 문자열 배열 strArr을 입력으로 받아 문제를 해결하는 함수입니다. 반환값으로 문자열 배열을 반환합니다.

int count = 0;: 유효한 문자열의 개수를 저장하기 위한 변수 count를 초기화합니다.

String ad = "ad";: "ad"라는 부분 문자열을 저장하는 변수입니다. 나중에 이 문자열을 포함하는지 검사할 때 사용됩니다.

for (int i = 0; i < strArr.length; i++) { ... }: 주어진 문자열 배열 strArr의 각 문자열에 대해서 반복문을 실행합니다.

if (!strArr[i].contains(ad)) { ... }: 현재 문자열이 "ad"를 포함하지 않는지 검사합니다. 포함하지 않는 경우 count 값을 증가시킵니다.

String[] answer = new String[count];: 유효한 문자열의 개수에 맞게 크기가 결정된 answer 배열을 생성합니다.

int index = 0;: answer 배열에 문자열을 저장할 때 사용될 인덱스 변수를 초기화합니다.

두 번째 반복문에서 유효한 문자열을 answer 배열에 저장하는 작업을 수행합니다. 검사하여 "ad"를 포함하지 않는 경우에만 answer 배열에 저장하며, 인덱스 값을 증가시키면서 저장합니다.

return answer;: 최종적으로 구성된 answer 배열을 반환합니다.
