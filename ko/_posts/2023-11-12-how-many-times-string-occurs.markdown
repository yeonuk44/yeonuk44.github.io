---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Count_How_Many_Times_String_Occurs
title: 문자열이 몇 번 등장하는지 세기(with.Java)
# title: Count how many times a string occurs (with.Java)
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
date: 2023-11-12 09:00:00 +0900
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

### "문자열이 몇 번 등장하는지 세기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 myString과 pat이 주어집니다.

myString에서 pat이 등장하는 횟수를 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| myString | pat   | result |
| -------- | ----- | ------ |
| "banana" | "ana" | 2      |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String myString, String pat) {
        int answer = 0;
        for(int i = pat.length() - 1; i < myString.length(); i++){
            String str = myString.substring(0, i + 1);
            if(str.endsWith(pat)){
                answer++;
            }
        }
        return answer;
    }
}
```

##### 풀이 설명

public int solution(String myString, String pat): 두 개의 문자열 파라미터 myString과 pat을 입력으로 받아서 문제를 해결하는 함수입니다. 결과로 정수형 값을 반환합니다.

int answer = 0;: 부분 문자열의 개수를 저장하기 위한 변수 answer를 초기화합니다.

for(int i = pat.length(); i < myString.length(); i++) { ... }: 주어진 문자열 myString의 각 문자에 대해서 반복문을 실행합니다. 시작 위치는 pat의 길이부터 시작합니다.

String str = myString.substring(0, i + 1);: 현재 위치까지의 부분 문자열을 생성합니다. substring 메소드를 사용하여 시작 인덱스 0부터 현재 인덱스 i까지의 부분 문자열을 생성합니다.

if(str.endsWith(pat)) { ... }: 생성한 부분 문자열 str이 주어진 문자열 pat로 끝나는지 검사합니다.

answer++;: 만약 부분 문자열이 pat로 끝난다면 answer 값을 1 증가시킵니다.

return answer;: 최종적으로 찾은 부분 문자열의 개수인 answer 값을 반환합니다.

이 코드는 주어진 문자열 myString의 부분 문자열 중에서 pat로 끝나는 부분 문자열의 개수를 세는 작업을 수행합니다. 코드는 문제를 정확하게 해결하고 있으며, endsWith 메소드를 통해 문자열의 끝 부분이 주어진 패턴과 일치하는지 검사합니다.
