---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_The_Median
title: Finding the Median (with.Java)
# title: Finding the Median (with.Java)
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
date: 2023-12-21 09:00:00 +0900
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

## "배열 두배 만들기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 배열 numbers가 매개변수로 주어집니다.

numbers의 각 원소에 두배한 원소를 가진 배열을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예시

| numbers                   | result                     |
| ------------------------- | -------------------------- |
| [1, 2, 3, 4, 5]           | [2, 4, 6, 8, 10]           |
| [1, 2, 100, -99, 1, 2, 3] | [2, 4, 200, -198, 2, 4, 6] |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] numbers) {
        for(int i = 0; i < numbers.length; i++){
            numbers[i] *= 2;
        }
        return numbers;
    }
}
```

#### 풀이 설명

public int[] solution(int[] numbers) : 함수 solution을 선언하고 정수 배열 numbers를 입력 매개변수로 받습니다. 함수는 정수 배열을 반환합니다.

for(int i = 0; i < numbers.length; i++){: 배열 numbers의 각 요소에 접근하기 위한 반복문을 시작합니다. i 변수는 반복문을 통해 배열의 인덱스를 나타냅니다.

numbers[i] \*= 2;: 현재 인덱스 i에 해당하는 배열 요소를 2배로 만듭니다. 이 코드는 현재 배열 요소의 값을 2로 곱하여 수정합니다.

}: 반복문의 끝을 표시합니다. 배열의 모든 요소를 처리한 후에 종료됩니다.

return numbers;: 변경된 배열 numbers를 함수의 반환 값으로 반환합니다. 따라서 이 함수는 주어진 배열의 모든 요소를 2배로 만든 후 그 결과를 반환합니다.
