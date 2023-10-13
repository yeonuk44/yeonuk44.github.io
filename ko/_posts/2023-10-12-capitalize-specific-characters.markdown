---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Capitalize_Specific_Characters
title: 특정한 문자를 대문자로 바꾸기(with.Java)
# title:  Capitalize specific characters (with.Java)
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
date: 2023-10-12 09:00:00 +0900
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

### 특정한 문자를 대문자로 바꾸기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

영소문자로 이루어진 문자열 my_string과 영소문자 1글자로 이루어진 문자열 alp가 매개변수로 주어질 때, my_string에서 alp에 해당하는 모든 글자를 대문자로 바꾼 문자열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| myString      | alp | result        |
| ------------- | --- | ------------- |
| "programmers" | "p" | "Programmers" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String my_string, String alp) {
        StringBuilder answer = new StringBuilder();
        for(int i = 0; i < my_string.length(); i++){
            char currentChar = my_string.charAt(i);
            if(currentChar == alp.charAt(0)){
                answer.append(Character.toUpperCase(currentChar));
            } else{
                answer.append(currentChar);
            }
        }
        return answer.toString();
    }
}
```

##### 풀이 설명

public String solution(String my_string, String alp): 두 개의 문자열 파라미터 my_string과 alp를 입력으로 받아서 문자열을 처리하는 함수입니다.

StringBuilder answer = new StringBuilder();: 결과 문자열을 담을 StringBuilder 객체를 생성합니다. 이 객체를 사용하여 문자열을 구성할 것입니다.

for(int i = 0; i < my_string.length(); i++) { ... }: 주어진 문자열 my_string의 각 문자에 대해서 반복문을 실행합니다.

char currentChar = my_string.charAt(i);: 현재 반복문에서 처리하고 있는 문자열의 문자를 currentChar 변수에 저장합니다.

if(currentChar == alp.charAt(0)) { ... } else { ... }: 현재 문자가 주어진 문자 alp와 같은지 비교합니다.

answer.append(Character.toUpperCase(currentChar));: 현재 문자가 주어진 문자 alp와 같다면 대문자로 변환하여 결과 문자열 answer에 추가합니다.

answer.append(currentChar);: 현재 문자가 주어진 문자 alp와 다르다면 그대로 유지하여 결과 문자열 answer에 추가합니다.

return answer.toString();: 최종적으로 answer에 저장된 문자열을 문자열 형태로 반환합니다.
