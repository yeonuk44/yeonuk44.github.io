---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_String_Case_Conversion_In_Arrays
title: 배열에서 문자열 대소문자 변환하기(with.Java)
# title: String Case Conversion in Arrays (with.Java)
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
date: 2023-11-04 09:00:00 +0900
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

### 배열에서 문자열 대소문자 변환하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 배열 strArr가 주어집니다.

모든 원소가 알파벳으로만 이루어져 있을 때, 배열에서 홀수번째 인덱스의 문자열은 모든 문자를 대문자로, 짝수번째 인덱스의 문자열은 모든 문자를 소문자로 바꿔서 반환하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| strArr                    | result                    |
| ------------------------- | ------------------------- |
| ["AAA","BBB","CCC","DDD"] | ["aaa","BBB","ccc","DDD"] |
| ["aBc","AbC"]             | ["abc","ABC"]             |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String[] solution(String[] strArr) {
        String[] answer = new String[strArr.length];
        for(int i = 0; i < strArr.length; i++){
            if(i % 2 == 0){
                answer[i] = strArr[i].toLowerCase();
            } else{
                answer[i] = strArr[i].toUpperCase();
            }
        }
        return answer;
    }
}
```

##### 풀이 설명

String[] answer = new String[strArr.length];: 결과를 저장할 문자열 배열 answer를 생성합니다. 입력 배열과 동일한 길이로 생성합니다.

for(int i = 0; i < strArr.length; i++) : 입력 배열 strArr를 반복하면서 각 문자열을 검사합니다.

if(i % 2 == 0) : 현재 인덱스 i가 짝수인 경우:

현재 문자열을 소문자로 변환하여 answer 배열에 저장합니다.

else : 현재 인덱스 i가 홀수인 경우:

현재 문자열을 대문자로 변환하여 answer 배열에 저장합니다.

return answer;: 모든 문자열에 대한 변환이 완료된 answer 배열을 반환합니다.

이 코드는 입력 배열의 짝수 인덱스에 있는 문자열을 소문자로 변환하고 홀수 인덱스에 있는 문자열을 대문자로 변환한 새로운 배열을 생성하여 반환합니다.
