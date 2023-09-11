---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_Flipping_String_Multiple_Times
title: Implementing Flipping a String Multiple Times (with.Java)
# title: Implementing Flipping a String Multiple Times (with.Java)

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
date: 2023-09-11 09:00:00 +0900
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

### 부분 문자열 이어 붙여 문자열 만드는 방법에 대하여(with.Java)

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

#### 문제

길이가 같은 문자열 배열 my_strings와 이차원 정수 배열 parts가 매개변수로 주어집니다.

parts[i]는 [s, e] 형태로, my_string[i]의 인덱스 s부터 인덱스 e까지의 부분 문자열을 의미합니다.

각 my_strings의 원소의 parts에 해당하는 부분 문자열을 순서대로 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: ["progressive", "hamburger", "hammer", "ahocorasick"]

queries: [[0, 4], [1, 2], [3, 5], [7, 7]]

result: "programmers"

예제를 풀어보면 각 부분 문자열을 순서대로 이어 붙인 문자열은 "programmers"입니다. 따라서 "programmers"를 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String[] my_strings, int[][] parts) {
        String answer = "";
        for(int i = 0; i < parts.length; i++){
            answer += my_strings[i].substring(parts[i][0], parts[i][1]+1);
        }
        return answer;
    }
}
```

##### 풀이 설명

로직대로 구현하기 위해 parts의 길이만큼 반복문을 순회하게 만든 뒤, String 타입의 answer에 my_strings의 문자열 요소를 substring 함수를 통해 저장합니다.

substring()함수 속 인자에 parts[i][0], parts[i][1]+1를 삽입했는데 이는 substring은 startIndex부터 시작해서 endIndex의 바로 전까지 반환해줍니다.

간단한 수식으로 이해를 돕자면 startIndex <= 순회 번호 < endIndex 이기 때문입니다.

문제에서 요구하는 index까지의 반환값을 얻기 위해선 +1 을 해줘야 <=가 되기 때문에 더해줬습니다.
