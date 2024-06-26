---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_To_Come_Next
title: 다음에 올 숫자 (with.Java)
# title: Number to come next (with.Java)
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
date: 2024-05-29 09:00:00 +0900
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

## "다음에 올 숫자 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

등차수열 혹은 등비수열 common이 매개변수로 주어질 때, 마지막 원소 다음으로 올 숫자를 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 2 < common의 길이 < 1,000
- -1,000 < common의 원소 < 2,000
- common의 원소는 모두 정수입니다.
- 등차수열 혹은 등비수열이 아닌 경우는 없습니다.
- 등비수열인 경우 공비는 0이 아닌 정수입니다.

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| common       | result |
| ------------ | ------ |
| [1, 2, 3, 4] | 5      |
| [2, 4, 8]    | 16     |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] common) {
        int answer = 0;
        if(common[1] - common[0] == common[2] - common[1]){
            answer = common[common.length - 1] + (common[1] - common[0]);
        }else{
            answer = common[common.length - 1] * (common[1] / common[0]);
        }
        return answer;
    }
}
```

### 풀이 리뷰

등차 수열 또는 등비 수열인지를 판별하고, 다음 항을 구하는 함수입니다.

주어진 배열의 인덱스 0, 1, 2에 해당하는 값이 등차 또는 등비 수열을 이루는지 확인합니다.

만약 등차 수열이라면, 배열의 마지막 요소에 (등차의 값)을 더하여 다음 항을 구합니다.

만약 등비 수열이라면, 배열의 마지막 요소에 (공비의 값)을 곱하여 다음 항을 구합니다.

구한 값을 반환합니다.
