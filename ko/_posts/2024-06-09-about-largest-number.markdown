---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Largest_Number
title: 가장 큰 수 (with. Java)
# title: Largest number (with. Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, sort]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-06-09 09:00:00 +0900
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

## "가장 큰 수 (with. Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

0 또는 양의 정수가 주어졌을 때, 정수를 이어 붙여 만들 수 있는 가장 큰 수를 알아내 주세요.

예를 들어, 주어진 정수가 [6, 10, 2]라면 [6102, 6210, 1062, 1026, 2610, 2106]를 만들 수 있고, 이중 가장 큰 수는 6210입니다.

0 또는 양의 정수가 담긴 배열 numbers가 매개변수로 주어질 때, 순서를 재배치하여 만들 수 있는 가장 큰 수를 문자열로 바꾸어 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- numbers의 길이는 1 이상 100,000 이하입니다.
- numbers의 원소는 0 이상 1,000 이하입니다.
- 정답이 너무 클 수 있으니 문자열로 바꾸어 return 합니다.

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| numbers           | return    |
| ----------------- | --------- |
| [6, 10, 2]        | "6210"    |
| [3, 30, 34, 5, 9] | "9534330" |

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public String solution(int[] numbers) {
        String[] answer = new String[numbers.length];

        for(int i = 0; i < numbers.length; i++){
            answer[i] = String.valueOf(numbers[i]);
        }

        Arrays.sort(answer, (m1, m2) -> (m2 + m1).compareTo(m1 + m2));

        if(answer[0].equals("0")){
            return "0";
        }

        return String.join("", answer);
    }
}
```

### 풀이 리뷰

solution 메서드는 정수 배열 numbers를 입력으로 받습니다.

결과를 저장할 문자열 배열 answer를 생성합니다. 이 배열의 크기는 numbers 배열의 길이와 동일합니다.

for 루프를 사용하여 numbers 배열의 각 요소를 문자열로 변환하여 answer 배열에 저장합니다.

Arrays.sort()를 사용하여 answer 배열을 정렬합니다. 정렬 기준은 주어진 숫자들을 조합하여 만들어지는 수의 크기를 비교합니다.

비교 기준은 두 문자열을 합쳐서 비교했을 때, 큰 값이 앞에 오도록 설정합니다. 즉, m2 + m1과 m1 + m2를 비교하여 내림차순으로 정렬합니다.

정렬된 배열의 첫 번째 요소가 "0"인 경우에는 주어진 숫자가 모두 0으로만 구성되어 있는 경우이므로 "0"을 반환합니다.

그렇지 않은 경우에는 String.join() 메서드를 사용하여 정렬된 배열을 합쳐서 반환합니다.

이 코드는 주어진 숫자 배열을 조합하여 만들 수 있는 가장 큰 수를 문자열로 반환하는 문제를 해결합니다.
