---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Average_Value_Of_Array
title: 배열의 평균값(with.Java)
# title: Average value of an array (with.Java)
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
date: 2024-01-08 09:00:00 +0900
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

## "배열의 평균값" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 배열 numbers가 매개변수로 주어집니다.

numbers의 원소의 평균값을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예시

| numbers                                      | result |
| -------------------------------------------- | ------ |
| [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]              | 5.5    |
| [89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99] | 94.0   |

### 문제에 대한 나의 풀이

```java
class Solution {
    public double solution(int[] numbers) {
        double answer = 0;
        for(int num : numbers){
            answer += num;
        }
        answer /= numbers.length;
        return answer;
    }
}
```

#### 풀이 설명

double answer = 0;: 결과 값을 저장할 변수 answer를 0으로 초기화합니다.

for (int num : numbers) : 배열 numbers에 있는 각 숫자(num)에 대해 반복합니다.

answer += num;: 각 숫자를 answer에 더하여 모든 숫자의 합을 계산합니다.

answer /= numbers.length;: 숫자들의 합을 배열의 길이(숫자의 개수)로 나누어 평균을 계산합니다.

return answer;: 계산된 평균 값을 반환합니다.
