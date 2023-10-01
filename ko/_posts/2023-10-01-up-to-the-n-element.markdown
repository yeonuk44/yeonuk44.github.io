---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Up_To_The_n_Element
title: n 번째 원소까지(with.Java)
# title: Up to the nth element (with.Java)

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
date: 2023-10-01 09:00:00 +0900
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

### n 번째 원소까지(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 리스트 num_list와 정수 n이 주어질 때, num_list의 첫 번째 원소부터 n 번째 원소까지의 모든 원소를 담은 리스트를 return하도록 solution 함수를 완성해주세요.

##### 입출력 예시

| num_list        | n   | result    |
| --------------- | --- | --------- |
| [2, 1, 6]       | 1   | [2]       |
| [5, 2, 1, 7, 5] | 7   | [5, 2, 1] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = new int[n];
        for(int i = 0; i < n; i++){
            answer[i] = num_list[i];
        }
        return answer;
    }
}
```

##### 풀이 설명

int[] answer = new int[n];: 결과를 저장할 정수 배열 answer를 생성합니다. 이 배열의 크기는 n으로 설정됩니다.

for(int i = 0; i < n; i++) : 반복문을 사용하여 num_list의 처음부터 n개의 요소를 추출합니다.

answer[i] = num_list[i];: 현재 인덱스 i의 num_list 요소를 answer 배열의 같은 인덱스에 복사합니다.

return answer;: 최종적으로 처음부터 n개의 요소로 이루어진 배열 answer를 반환합니다.
