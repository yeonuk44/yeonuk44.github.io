---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sorting_String_2
title: 문자열 정렬하기 2 (with.Java)
# title: Sorting strings 2 (with.Java)
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
date: 2024-04-23 09:00:00 +0900
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

## "문자열 정렬하기 2 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

영어 대소문자로 이루어진 문자열 my_string이 매개변수로 주어질 때, my_string을 모두 소문자로 바꾸고 알파벳 순서대로 정렬한 문자열을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 0 < my_string < 100

#### 입출력 예시

| my_string | result   |
| --------- | -------- |
| "Bcad"    | "abcd"   |
| "heLLo"   | "ehllo"  |
| "Python"  | "hnopty" |

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public String solution(String my_string) {
        String answer = my_string.toLowerCase();

        char[] chars = answer.toCharArray();
        Arrays.sort(chars);
        answer = new String(chars);
        return answer;
    }
}
```

### 풀이 설명

- 소문자 변환: toLowerCase 메서드를 사용하여 주어진 문자열을 소문자로 변환합니다.
- 문자 배열로 변환 및 정렬: toCharArray 메서드를 사용하여 문자열을 문자 배열로 변환하고, Arrays.sort 메서드를 사용하여 문자 배열을 알파벳 순으로 정렬합니다.
- 문자열로 변환: 정렬된 문자 배열을 다시 문자열로 변환하여 answer에 저장합니다.
- 결과 반환: 최종적으로 정렬된 문자열을 반환합니다.

**코드 장점**

- 문자열 정렬 간편성: Java의 내장 메서드를 활용하여 간편하게 문자열을 소문자로 변환하고 정렬할 수 있습니다.
- 코드 간결성: 간단하면서도 효과적인 방법으로 문자열을 처리하고 있습니다.

**코드 단점**

- 유니코드 문자 처리 부재: 현재 코드는 ASCII 문자에 대한 정렬을 수행하고 있습니다. 유니코드 문자를 올바르게 처리하기 위해서는 다른 방식을 고려해야 합니다.
- 문자열 불변성 무시: 문자열은 불변(immutable)하므로 정렬된 문자 배열을 다시 문자열로 변환하는 과정이 불필요하게 보일 수 있습니다. 이 부분을 최적화할 수 있습니다.
- 문자열이 null일 때 예외처리 부재: 현재 코드는 주어진 문자열이 null일 때의 처리를 고려하지 않고 있습니다. null에 대한 예외 처리를 추가하는 것이 좋습니다.
- 문자열에 공백이 포함된 경우 처리 부재: 현재 코드는 문자열 내의 공백을 고려하지 않고 정렬하고 있습니다. 만약 공백도 정렬에 포함시키고 싶다면 해당 부분을 수정해야 합니다.
