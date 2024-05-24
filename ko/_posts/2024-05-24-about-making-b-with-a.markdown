---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Making_B_With_A
title: A로 B 만들기 (with.Java)
# title: Making B with A (with.Java)
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
date: 2024-05-24 09:00:00 +0900
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

## "A로 B 만들기 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 before와 after가 매개변수로 주어질 때, before의 순서를 바꾸어 after를 만들 수 있으면 1을, 만들 수 없으면 0을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 0 < before의 길이 == after의 길이 < 1,000
- before와 after는 모두 소문자로 이루어져 있습니다.

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| before  | after   | result |
| ------- | ------- | ------ |
| "olleh" | "hello" | 1      |
| "allpe" | "apple" | 0      |

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public int solution(String before, String after) {

        char[] beforeArray = before.toCharArray();
        char[] afterArray = after.toCharArray();
        Arrays.sort(beforeArray);
        Arrays.sort(afterArray);

        return Arrays.equals(beforeArray, afterArray) ? 1 : 0;
    }
}
```

### 풀이 리뷰

먼저, 입력된 두 문자열 before와 after를 각각 문자 배열(char[])로 변환합니다.

Arrays.sort() 함수를 사용하여 두 문자 배열을 알파벳 순으로 정렬합니다.

이렇게 하면 두 문자열의 각 문자가 정렬된 상태가 됩니다.

Arrays.equals() 함수를 사용하여 정렬된 두 문자 배열이 서로 같은지를 확인합니다.

이 함수는 두 배열이 같은지를 비교하여 true 또는 false를 반환합니다.

만약 정렬된 두 문자 배열이 같다면, 즉, 두 문자열이 같은 문자들을 가지고 있다면, 1을 반환합니다.

그렇지 않으면 0을 반환합니다.

입력된 문자열이 동일한 문자들로 이루어져 있는지를 간단하게 확인하기 위해 문자열을 정렬하여 비교하는 방법을 사용합니다.
