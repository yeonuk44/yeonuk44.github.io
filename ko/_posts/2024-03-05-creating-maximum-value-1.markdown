---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Creating_Maximum_Value_1
title: 최댓값 만들기 1 (with.Java)
# title: Creating maximum value 1 (with.Java)
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
date: 2024-03-05 09:00:00 +0900
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

## "최댓값 만들기 1" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 배열 numbers가 매개변수로 주어집니다.

numbers의 원소 중 두 개를 곱해 만들 수 있는 최댓값을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 0 ≤ numbers의 원소 ≤ 10,000
- 2 ≤ numbers의 길이 ≤ 100

#### 입출력 예시

| numbers               | result |
| --------------------- | ------ |
| [1, 2, 3, 4, 5]       | 20     |
| [0, 31, 24, 10, 1, 9] | 744    |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int solution(int[] numbers) {
        int answer = 1;
        Arrays.sort(numbers);
        int endIdx = numbers.length - 1;
        for(int i = endIdx; i >= endIdx - 1; i--){
            answer *= numbers[i];
        }
        return answer;
    }
}
```

### 풀이 설명

- Arrays.sort(numbers): 배열을 정렬한다.
- endIdx: 배열의 마지막 인덱스를 계산한다.
- for 문을 이용하여 가장 큰 두 숫자를 선택하고 곱한다.

**코드 장점**

- 정렬을 활용: 정렬을 통해 가장 큰 숫자를 빠르게 선택할 수 있다.
