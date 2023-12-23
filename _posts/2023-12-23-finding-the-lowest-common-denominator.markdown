---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_The_Lowest_Common_Denominator
title: Finding the Lowest Common Denominator (with.Java)
# title: Finding the Lowest Common Denominator (with.Java)
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
date: 2023-12-23 09:00:00 +0900
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

## "배열 자르기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 배열 numbers와 정수 num1, num2가 매개변수로 주어질 때, numbers의 num1번 째 인덱스부터 num2번째 인덱스까지 자른 정수 배열을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

2 ≤ numbers의 길이 ≤ 30

0 ≤ numbers의 원소 ≤ 1,000

0 ≤num1 < num2 < numbers의 길이

#### 입출력 예시

| numbers         | num1 | num2 | result    |
| --------------- | ---- | ---- | --------- |
| [1, 2, 3, 4, 5] | 1    | 3    | [2 ,3, 4] |
| [1, 3, 5]       | 1    | 2    | [3, 5]    |

### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int[] solution(int[] numbers, int num1, int num2) {
        int[] answer = Arrays.copyOfRange(numbers, num1, num2 + 1);
        return answer;
    }
}
```

#### 풀이 설명

Java에서 배열을 슬라이스하는 메서드는 직접적으로 제공되지 않습니다.

하지만 배열의 일부분을 복사하여 새로운 배열을 만들 수 있습니다.

예를 들어, Arrays.copyOfRange() 메서드를 사용하여 배열을 슬라이스하는 방법이 있습니다. 위의 풀이 방법은 해당 메서드를 통해 새로운 배열에 슬라이스해 복사하는 방법으로 해결하였습니다.

위 예제에서 Arrays.copyOfRange(numbers, num1, num2 + 1)는 numbers배열에서 num1부터 num2까지의 부분 배열을 만듭니다. +1을 하는 이유는 num2도 포함하기 위함입니다.
