---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Length_Of_Overlapping_Line_Segments
title: Length of overlapping line segments (with.Java)
# title: Length of overlapping line segments (with.Java)
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
date: 2024-05-15 09:00:00 +0900
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

## "평행 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

점 네 개의 좌표를 담은 이차원 배열 dots가 다음과 같이 매개변수로 주어집니다.

[[x1, y1], [x2, y2], [x3, y3], [x4, y4]]

주어진 네 개의 점을 두 개씩 이었을 때, 두 직선이 평행이 되는 경우가 있으면 1을 없으면 0을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- dots의 길이 = 4
- dots의 원소는 [x, y] 형태이며 x, y는 정수입니다.
- 0 ≤ x, y ≤ 100
- 서로 다른 두개 이상의 점이 겹치는 경우는 없습니다.
- 두 직선이 겹치는 경우(일치하는 경우)에도 1을 return 해주세요.
- 임의의 두 점을 이은 직선이 x축 또는 y축과 평행한 경우는 주어지지 않습니다.

#### 입출력 예시

<!-- | keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] | -->

| dots                              | result |
| --------------------------------- | ------ |
| [[1, 4], [9, 2], [3, 8], [11, 6]] | 1      |
| [[3, 5], [4, 1], [2, 4], [5, 10]] | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[][] dots) {
        int answer = 0;
        for(int i =0; i<dots.length;i++) {

                float temp =gradient(dots[i],dots[(i+1)%4]);
                float temp2 =gradient(dots[(i+2)%4],dots[(i+3)%4]);

                if(temp==temp2) {
                    answer = 1;
                }
        }
        return answer;
    }
    public static float gradient(int[]a1,int[]a2) {
        float denom,mole;

            denom= a1[0]-a2[0];
            mole= a1[1]-a2[1];

        return mole/denom;
    }
}
```

### 풀이 설명

solution 메서드는 주어진 점 배열인 dots를 인자로 받습니다.

answer 변수는 사각형 여부를 나타내는 결과를 저장합니다.

초기에는 0으로 설정되어 있습니다.

for 루프는 dots 배열을 순회합니다.

이 때 i번째 점을 기준으로 해당 점을 제외한 다른 세 개의 점들 간의 기울기를 비교합니다.

gradient 메서드는 두 점 사이의 기울기를 계산합니다. 이를 통해 두 점이 이루는 선의 기울기를 구할 수 있습니다.

만약 모든 변의 기울기가 같다면 (temp와 temp2가 같다면) answer를 1로 설정합니다.

모든 루프를 마친 뒤에 answer 값을 반환합니다.

주어진 점들을 이용하여 사각형을 이루는지 확인하는 간단한 방법을 제공합니다.

주어진 문제에 따라 점의 개수와 배열의 형태가 변경될 수 있지만, 해당 메서드를 사용하여 다각형의 형태를 파악할 수 있습니다.
