---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_National_Competition_Selection_Test
title: National Competition Selection Test (with.Java)
# title: National Competition Selection Test (with.Java)
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
date: 2023-11-09 09:00:00 +0900
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

### "문자열 정수의 합" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

한 자리 정수로 이루어진 문자열 num_str이 주어질 때, 각 자리수의 합을 return하도록 solution 함수를 완성해주세요.

##### 입출력 예시

| num_str     | result |
| ----------- | ------ |
| "123456789" | 45     |
| "1000000"   | 1      |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String num_str) {
        int answer = 0;
        for(int i = 0; i < num_str.length(); i++){
            answer += Integer.parseInt(String.valueOf(num_str.charAt(i)));
        }
        return answer;
    }
}
```

##### 풀이 설명

int answer = 0;: 결과를 저장할 변수 answer를 초기화합니다. 초기값은 0입니다.

for(int i = 0; i < num_str.length(); i++): 입력 문자열 num_str을 반복하면서 각 문자를 검사합니다.

num_str.charAt(i): 현재 인덱스 i에 위치한 문자를 가져옵니다.

String.valueOf(...): 문자를 문자열로 변환합니다.

Integer.parseInt(...): 문자열을 정수로 변환합니다. 이렇게 변환한 값을 answer에 더합니다.

return answer;: 문자열에 포함된 숫자들을 모두 더한 결과를 반환합니다.

이 코드는 입력 문자열에 포함된 숫자를 모두 더하여 그 합을 반환합니다. 문자열을 문자 단위로 반복하면서 각 문자를 정수로 변환하여 더하고, 최종적으로 더한 합을 반환합니다.
