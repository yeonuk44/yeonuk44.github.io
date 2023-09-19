---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_The_Nearest_1
title: 가까운 1 찾기, 주어진 인덱스를 통해 조건에 부합하는 수를 출력하는 방법에 대하여(with.Java)
# title: How to find the nearest 1, output the number that meets a condition via a given index (with.Java)

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
date: 2023-09-19 09:00:00 +0900
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

### 가까운 1 찾기, 주어진 인덱스를 통해 조건에 부합하는 수를 출력하는 방법에 대하여(with.Java)

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr가 주어집니다. 이때 arr의 원소는 1 또는 0입니다. 정수 idx가 주어졌을 때, idx보다 크면서 배열의 값이 1인 가장 작은 인덱스를 찾아서 반환하는 solution 함수를 완성해 주세요.

단, 만약 그러한 인덱스가 없다면 -1을 반환합니다.

##### 입출력 예시

my_string: [0, 0, 0, 1]

idx: 1

result: 3

1보다 크면서 원소가 1인 가장 작은 인덱스는 3입니다. 따라서 3을 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] arr, int idx) {
        for(int i = idx; i < arr.length; i++) {
            if(arr[i] == 1) {
                return i;
            }
        }
        return -1;
    }
}
```

##### 풀이 설명

이 클래스는 주어진 정수 배열 arr와 정수 idx에 대해 다음과 같은 작업을 수행하는 solution 메서드를 정의하고 있습니다:

idx부터 arr의 끝까지 반복문을 수행합니다. idx는 시작 인덱스로, arr의 이 위치에서 시작하여 배열의 끝까지 검사합니다.

반복문 내에서 현재 인덱스 i의 arr[i] 값이 1인지 확인합니다. 만약 arr[i]가 1이면, i를 반환하고 메서드를 종료합니다. 이는 idx 이상의 인덱스 중 값이 1인 첫 번째 인덱스를 찾는 것과 같습니다.

반복문이 완료되고 값이 1인 인덱스를 찾지 못한 경우, -1을 반환합니다. 이는 문제의 요구 사항대로 idx보다 크면서 배열의 값이 1인 인덱스가 없는 경우에 해당합니다.

예를 들어, arr이 [1, 1, 1, 1, 0]이고 idx가 3인 경우, idx부터 시작하여 값이 1인 첫 번째 인덱스는 3이므로 결과로 3을 반환합니다.
