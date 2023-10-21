---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Delimiting_Spaces_2
title: Delimiting Spaces 2 (with.Java)
# title: Delimiting Spaces 2 (with.Java)
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
date: 2023-10-20 09:00:00 +0900
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

### rny_string 구현하는 것에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

'm'과 "rn"이 모양이 비슷하게 생긴 점을 활용해 문자열에 장난을 하려고 합니다.

문자열 rny_string이 주어질 때, rny_string의 모든 'm'을 "rn"으로 바꾼 문자열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| rny_string    | result         |
| ------------- | -------------- |
| "masterpiece" | "rnasterpiece" |
| "programmers" | "programmers"  |
| "jerry"       | "jerry"        |
| "burn"        | "burn"         |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String rny_string) {
        StringBuilder answer = new StringBuilder(rny_string);
        for(int i = 0; i < answer.length(); i++){
            if(answer.charAt(i) == 'm'){
                answer.replace(i,i,"rn");
            }
        }
        return answer.toString();
    }
}
```

##### 풀이 설명

StringBuilder answer = new StringBuilder(rny_string);: 주어진 문자열 rny_string을 수정할 수 있는 StringBuilder 객체로 변환합니다. StringBuilder는 문자열을 효율적으로 수정하기 위한 클래스입니다.

for(int i = 0; i < answer.length(); i++): 문자열을 한 글자씩 순회하는 루프를 시작합니다. 루프는 문자열의 길이만큼 반복됩니다.

if(answer.charAt(i) == 'm'): 현재 인덱스 i의 문자가 'm'인지 확인합니다.

answer.replace(i, i + 1, "rn");: 'm'을 "rn"으로 대체합니다. replace 메소드는 시작 인덱스 i와 끝 인덱스 i + 1 사이의 문자열을 "rn"으로 대체합니다.

return answer.toString();: StringBuilder 객체를 다시 문자열로 변환하여 결과를 반환합니다.

이렇게 구현된 코드는 입력된 문자열에서 'm' 문자를 모두 "rn"으로 대체하여 새로운 문자열을 생성하고 반환합니다. 문자열 수정에 StringBuilder를 사용하여 효율적으로 작업하고 있습니다.
