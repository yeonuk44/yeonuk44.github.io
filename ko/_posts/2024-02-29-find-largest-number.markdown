---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_Largest_Number
title: 가장 큰 수 찾기 (with.Java)
# title: Find largest number (with.Java)
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
date: 2024-02-29 09:00:00 +0900
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

## "가장 큰 수 찾기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 배열 array가 매개변수로 주어질 때, 가장 큰 수와 그 수의 인덱스를 담은 배열을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 1 ≤ array의 길이 ≤ 100
- 0 ≤ array 원소 ≤ 1,000
- array에 중복된 숫자는 없습니다.

#### 입출력 예시

| array          | result  |
| -------------- | ------- |
| [1, 8, 3]      | [8, 1]  |
| [9, 10, 11, 8] | [11, 2] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] array) {
        int[] answer = new int[2];
        int temp = 0;
        int idx = 0;
        for(int i = 0; i < array.length; i++){
            if(temp < array[i]){
                temp = array[i];
                idx = i;
            }
        }

        answer[0] = temp;
        answer[1] = idx;
        return answer;
    }
}
```

### 풀이 설명

- 먼저 크기가 2인 int 배열 answer가 선언되고 초기화됩니다. 이 배열은 결과값을 저장하기 위한 용도로 사용됩니다.
- 또한, int 변수 temp와 idx도 선언되고 0으로 초기화됩니다.
- temp는 현재까지의 최댓값을, idx는 해당 최댓값의 인덱스를 저장하는 변수입니다.
- 그 다음, for 문을 통해 배열을 순회합니다.
- 배열의 각 요소에 접근하여 temp와 비교합니다. 만약 현재 요소가 temp보다 크다면, temp와 idx를 갱신합니다.
- 즉, 현재까지의 최댓값보다 큰 값을 만나면 temp와 idx를 갱신하여 해당 값과 인덱스를 기록합니다.
- for 문이 종료되면, temp와 idx는 가장 큰 값과 해당 값의 인덱스를 가지게 됩니다.
- 이 값을 answer 배열에 저장하고, answer 배열을 반환합니다.
