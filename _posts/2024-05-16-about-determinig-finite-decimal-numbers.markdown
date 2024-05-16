---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Determinig_Finite_Decimal_Numbers
title: Determining finite decimal numbers (with.Java)
# title: Determining finite decimal numbers (with.Java)
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
date: 2024-05-16 09:00:00 +0900
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

## "겹치는 선분의 길이 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

선분 3개가 평행하게 놓여 있습니다.

세 선분의 시작과 끝 좌표가 [[start, end], [start, end], [start, end]] 형태로 들어있는 2차원 배열 lines가 매개변수로 주어질 때, 두 개 이상의 선분이 겹치는 부분의 길이를 return 하도록 solution 함수를 완성해보세요.

선분이 두 개 이상 겹친 곳은 [-2, -1], [0, 1]로 길이 2만큼 겹쳐있습니다.

#### 제한사항

- lines의 길이 = 3
- lines의 원소의 길이 = 2
- 모든 선분은 길이가 1 이상입니다.
- lines의 원소는 [a, b] 형태이며, a, b는 각각 선분의 양 끝점 입니다.
- -100 ≤ a < b ≤ 100

#### 입출력 예시

<!-- | keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] | -->

| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[][] lines) {
        int answer = 0;
        int[] points = new int[201];

        for(int[] line : lines){
            int start = line[0]+100;
            int end = line[1]+100;

            for(int i = start; i < end; i++){
                points[i] += 1;
            }
        }

        for(int i : points){
            if(i > 1){
                answer++;
            }
        }
        return answer;
    }
}
```

### 풀이 설명

answer 변수는 교차하는 지점의 수를 저장하는 변수입니다.

초기에는 0으로 설정됩니다.

선분의 시작과 끝을 나타내는 배열 points를 생성합니다.

이 배열의 크기는 선분의 범위에 따라 결정됩니다.

여기서는 -100부터 100까지의 범위로 설정하여 전체 201개의 점을 표현합니다.

lines 배열을 순회하면서 각 선분의 시작과 끝을 구합니다.

여기서는 각 선분을 points 배열 상의 인덱스로 변환하여 카운트합니다.

해당 선분이 지나가는 모든 점들을 1씩 증가시킵니다.

모든 선분을 처리한 후, points 배열을 순회하면서 각 점의 값이 1보다 크면 해당 지점에서 교차하는 선분이 있음을 의미하므로 answer를 증가시킵니다.

최종적으로 answer 값을 반환합니다.

이 코드를 통해 선분들이 교차하는 지점의 수를 효율적으로 계산할 수 있습니다.

입력된 선분들의 범위에 따라 배열의 크기가 달라질 수 있으나, 이 알고리즘은 임의의 범위에 대해서도 동작할 수 있도록 구현되어 있습니다.

여기서 주목할 점은 선분을 표현하기 위해 배열 points를 생성한 후, 해당 선분의 범위를 1씩 증가시키는 방식을 사용한 것입니다.

이를 통해 각 점이 몇 개의 선분에 걸쳐있는지를 쉽게 계산할 수 있습니다.
