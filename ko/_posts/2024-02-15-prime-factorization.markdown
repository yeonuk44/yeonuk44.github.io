---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Prime_Factorization
title: 소인수분해(Java, HashSet, ArrayList, Set, List)
# title: Prime factorization (Java, HashSet, ArrayList, Set, List)
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
date: 2024-02-15 09:00:00 +0900
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

## "모음 제거" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

영어에선 a, e, i, o, u 다섯 가지 알파벳을 모음으로 분류합니다.

문자열 my_string이 매개변수로 주어질 때 모음을 제거한 문자열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- my_string은 소문자와 공백으로 이루어져 있습니다.
- 1 ≤ my_string의 길이 ≤ 1,000

#### 입출력 예시

| my_string          | result      |
| ------------------ | ----------- |
| "bus"              | "bs"        |
| "nice to meet you" | "nc t mt y" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String my_string) {
        StringBuilder answer = new StringBuilder();
        char[] arrString = my_string.toCharArray();

        for(char charString : arrString){
            if(charString != 'a' && charString != 'e' && charString != 'i' && charString != 'o' && charString != 'u'){
                answer.append(charString);
            }
        }
        return answer.toString();
    }
}
```

### 풀이 설명

solution(String my_string): 주어진 문자열 my_string에서 모음을 제외한 문자들을 추출하여 반환합니다.

StringBuilder를 사용하여 문자열을 효율적으로 처리합니다.

문자열을 문자 배열로 변환하고, 각 문자에 대해 모음인지 검사하여 모음이 아닌 경우 StringBuilder에 추가합니다.

최종적으로 StringBuilder를 문자열로 변환하여 결과를 반환합니다.

**코드 장점**

- 효율적인 문자열 처리: StringBuilder를 사용하여 문자열 처리를 효율적으로 수행한다.
- 간결한 구현: 각 문자에 대한 모음 검사를 통해 간결한 구현을 제공한다.

**코드 단점**

- 하드코딩된 모음 리스트: 모음을 검사할 때 'a', 'e', 'i', 'o', 'u'를 하드코딩하여 사용하고 있어, 나중에 모음이 변경될 경우 코드를 수정해야 한다.
