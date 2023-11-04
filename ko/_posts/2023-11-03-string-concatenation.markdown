---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_String_Concatenation
title: 문자열 묶기(with.Java)
# title: String Concatenation (with.Java)
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
date: 2023-11-03 09:00:00 +0900
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

### 문자열 묶기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 배열 strArr이 주어집니다.

strArr의 원소들을 길이가 같은 문자열들끼리 그룹으로 묶었을 때 가장 개수가 많은 그룹의 크기를 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| strArr                    | result |
| ------------------------- | ------ |
| ["a","bc","d","efg","hi"] | 2      |

#### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int solution(String[] strArr) {
        int[] temp = new int[strArr.length];

        for (int i = 0; i < strArr.length; i++) {
            temp[i] = strArr[i].length();
        }

        Map<Integer, Integer> lengthCount = new HashMap<>();

        for (int len : temp) {
            lengthCount.put(len, lengthCount.getOrDefault(len, 0) + 1);
        }

        int maxCount = 0;
        for (int count : lengthCount.values()) {
            if (count > maxCount) {
                maxCount = count;
            }
        }

        return maxCount;
    }
}
```

##### 풀이 설명

temp 배열 생성: 문자열 배열 strArr의 각 문자열의 길이를 저장하기 위한 temp 배열을 생성합니다.

길이 그룹화를 위한 HashMap 생성: lengthCount라는 이름의 HashMap을 생성합니다. 이 해시맵은 문자열 길이를 키로 지정하고, 해당 길이의 문자열 개수를 값으로 저장합니다.

반복문을 통한 그룹화 및 개수 계산: 문자열 배열 strArr을 반복하면서, 각 문자열의 길이를 temp 배열에 저장하고, 동시에 lengthCount 해시맵에 길이를 키로 가지는 엔트리가 있는지 확인하고, 없다면 새로운 엔트리를 생성하고 값을 1로 초기화합니다. 이미 존재하는 경우에는 해당 키의 값을 1 증가시킵니다.

최대 중복 횟수 계산: lengthCount 해시맵에서 모든 값(중복 횟수)을 순회하며, 최대 중복 횟수(maxCount)를 찾습니다.

최대 중복 횟수 반환: 최대 중복 횟수(maxCount)를 반환합니다.
