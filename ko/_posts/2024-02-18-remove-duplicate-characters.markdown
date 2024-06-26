---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Remove_Duplicate_Characters
title: 중복된 문자 제거(with.Java)
# title: Remove duplicate characters (with.Java)
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
date: 2024-02-18 09:00:00 +0900
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

## "중복된 문자 제거" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 my_string이 매개변수로 주어집니다.

my_string에서 중복된 문자를 제거하고 하나의 문자만 남긴 문자열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ my_string ≤ 110
- my_string은 대문자, 소문자, 공백으로 구성되어 있습니다.
- 대문자와 소문자를 구분합니다.
- 공백(" ")도 하나의 문자로 구분합니다.
- 중복된 문자 중 가장 앞에 있는 문자를 남깁니다.

#### 입출력 예시

| my_string          | result        |
| ------------------ | ------------- |
| "people"           | "peol"        |
| "We are the world" | "We arthwold" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public String solution(String my_string) {
        StringBuilder answer = new StringBuilder();
        Set<String> set = new HashSet<>();
        char[] arrMyString = my_string.toCharArray();

        for(char ch : arrMyString){
            if(set.add(String.valueOf(ch))){
                answer.append(ch);
            }
        }

        return answer.toString();
    }
}
```

### 풀이 설명

- HashSet 활용: Set<String> set = new HashSet<>();를 통해 중복을 허용하지 않는 HashSet을 생성한다.
- 문자열 순회: 문자열을 문자 배열로 변환한 후, for-each문을 사용하여 각 문자를 순회한다.
- 중복 제거: set.add(String.valueOf(ch))를 통해 HashSet에 문자를 추가하는데, 만약 이미 존재하는 문자라면 add 메서드는 false를 반환하고, 새로운 문자라면 true를 반환한다.
- 유일한 문자 추가: 새로운 문자인 경우에만 answer.append(ch)를 통해 결과 문자열에 해당 문자를 추가한다.
- 결과 반환: 모든 문자를 순회하고 중복된 문자를 제거한 후, 최종적으로 결과 문자열을 toString() 메서드를 통해 반환한다.

**코드 장점**

- 간결한 로직: 중복된 문자를 제거하고 유일한 문자만 남기는 간단하면서도 효과적인 로직을 사용하고 있다.
- HashSet 활용: HashSet은 중복된 값을 효과적으로 제거할 수 있는 자료구조로, 중복 검사에 용이하다.
- 문자열 조작: StringBuilder를 사용하여 문자열을 효율적으로 조작하고 있다.

**코드 단점**

- 대소문자 구분: 현재 코드는 대소문자를 구분하여 중복 문자를 처리하고 있다. 만약 대소문자를 구분하지 않고 중복을 처리하려면 추가적인 로직이 필요하다.
- 결과 문자열 순서: 현재 코드는 문자열의 순서를 유지하지 않고 중복을 제거한다. 만약 입력 문자열의 순서를 유지하면서 중복을 제거하려면 LinkedHashSet 등을 사용해야 한다.
- 문자열 변환 오버헤드: 문자를 String.valueOf(ch)를 통해 문자열로 변환하는 부분이 반복되어 오버헤드를 일으킬 수 있다. 특히 큰 문자열에 대한 처리에서 성능 저하의 원인이 될 수 있다.
