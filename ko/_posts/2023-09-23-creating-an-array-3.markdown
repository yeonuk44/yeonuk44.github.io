---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Creating_An_Array_3
title: 배열 만들기 3 (with.Java)
# title: Creating an Array 3 (with.Java)

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
date: 2023-09-23 09:00:00 +0900
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

### 배열 만들기 3 (with.Java)에 대하여

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr와 2개의 구간이 담긴 배열 intervals가 주어집니다.

intervals는 항상 [[a1, b1], [a2, b2]]의 꼴로 주어지며 각 구간은 닫힌 구간입니다. 닫힌 구간은 양 끝값과 그 사이의 값을 모두 포함하는 구간을 의미합니다.

이때 배열 arr의 첫 번째 구간에 해당하는 배열과 두 번째 구간에 해당하는 배열을 앞뒤로 붙여 새로운 배열을 만들어 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| arr             | intervals        | result                   |
| --------------- | ---------------- | ------------------------ |
| [1, 2, 3, 4, 5] | [[1, 3], [0, 4]] | [2, 3, 4, 1, 2, 3, 4, 5] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] arr, int[][] intervals) {
        int[] answer;
        int[] temp1;
        int[] temp2;
        int a1 = intervals[0][0];
        int b1 = intervals[0][1];
        int a2 = intervals[1][0];
        int b2 = intervals[1][1];

        temp1 = new int[b1 - a1 + 1];
        for(int l = a1; l <= b1; l++) {
            temp1[l - a1] = arr[l];
        }

        temp2 = new int[b2 - a2 + 1];
        for(int l = a2; l <= b2; l++) {
            temp2[l - a2] = arr[l];
        }

        answer = new int[temp1.length + temp2.length];
        for(int i = 0; i < temp1.length; i++) {
            answer[i] = temp1[i];
        }
        int e = 0;
        for(int i = temp1.length; i < answer.length; i++) {
            answer[i] = temp2[e++];
        }
        return answer;
    }
}
```

##### 풀이 설명

int[] answer;, int[] temp1;, int[] temp2;: 결과를 저장할 배열 answer와 두 개의 임시 배열 temp1 및 temp2를 선언합니다.

int a1 = intervals[0][0];, int b1 = intervals[0][1];, int a2 = intervals[1][0];, int b2 = intervals[1][1];: 주어진 구간 intervals에서 첫 번째와 두 번째 구간의 시작과 끝을 추출합니다.

temp1 = new int[b1 - a1 + 1];: 첫 번째 구간의 크기에 맞는 temp1 배열을 생성합니다.

for(int l = a1; l <= b1; l++) {: 첫 번째 구간을 반복하며 해당 구간의 요소를 temp1 배열에 복사합니다.

temp2 = new int[b2 - a2 + 1];: 두 번째 구간의 크기에 맞는 temp2 배열을 생성합니다.

for(int l = a2; l <= b2; l++) {: 두 번째 구간을 반복하며 해당 구간의 요소를 temp2 배열에 복사합니다.

answer = new int[temp1.length + temp2.length];: 결과 배열 answer의 크기를 두 개의 임시 배열의 크기 합으로 설정합니다.

첫 번째 구간(temp1)의 요소들을 answer 배열의 앞 부분에 복사합니다.

두 번째 구간(temp2)의 요소들을 answer 배열의 첫 번째 구간 다음에 복사합니다.

return answer;: 최종적으로 temp1과 temp2 구간의 요소들이 결합된 배열 answer를 반환합니다.
