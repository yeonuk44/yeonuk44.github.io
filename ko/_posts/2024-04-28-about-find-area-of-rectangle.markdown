---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_Area_Of_Rectangle
title: 직사각형 넓이 구하기(with.Java)
# title: Find the area of a rectangle (with.Java)
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
date: 2024-04-28 09:00:00 +0900
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

## "직사각형 넓이 구하기(with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

2차원 좌표 평면에 변이 축과 평행한 직사각형이 있습니다.

직사각형 네 꼭짓점의 좌표 [[x1, y1], [x2, y2], [x3, y3], [x4, y4]]가 담겨있는 배열 dots가 매개변수로 주어질 때, 직사각형의 넓이를 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- dots의 길이 = 4
- dots의 원소의 길이 = 2
- 256 < dots[i]의 원소 < 256
- 잘못된 입력은 주어지지 않습니다.

#### 입출력 예시

<!-- | array                | height | result |
| -------------------- | ------ | ------ |
| [149, 180, 192, 170] | 167    | 3      |
| [180, 120, 140]      | 190    | 0      | -->

| dots                                 | result |
| ------------------------------------ | ------ |
| [[1, 1], [2, 1], [2, 2], [1, 2]]     | 1      |
| [[-1, -1], [1, 1], [1, -1], [-1, 1]] | 4      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[][] dots) {
        int answer = 0;
        int x = dots[0][0];
        int y = dots[0][1];
        int weight = 0;
        int height = 0;

        for(int i = 1; i < dots.length; i++){
            if(x != dots[i][0]){
                weight = Math.abs(x - dots[i][0]);
            }
            if(y != dots[i][1]){
                height = Math.abs(y - dots[i][1]);
            }
        }

        answer = weight * height;
        return answer;
    }
}
```

### 풀이 설명

- 첫 번째 점의 좌표 저장: 주어진 점들 배열에서 첫 번째 점의 x 좌표와 y 좌표를 변수 x와 y에 저장합니다.
- 가로 길이 및 세로 길이 계산: 두 번째 점부터 마지막 점까지 반복하면서 x 좌표의 차이와 y 좌표의 차이를 구하여 가로 길이 width와 세로 길이 height를 각각 계산합니다.
- 사각형의 넓이 계산: 가로 길이와 세로 길이를 곱하여 사각형의 넓이를 구합니다.
- 결과 반환: 구한 사각형의 넓이를 answer 변수에 저장하고 반환합니다.

**코드 장점**

- 첫 번째 점을 기준으로 가로와 세로 길이 계산: 주어진 점들 중 첫 번째 점을 기준으로 가로와 세로 길이를 계산하여 사각형의 넓이를 구합니다.
- 가로와 세로 길이의 절대값 계산: 두 점 사이의 거리를 절대값으로 계산하여 가로와 세로 길이를 구합니다.

**코드 단점**

- 점의 순서에 따른 사각형의 방향: 점의 순서에 따라 사각형의 방향이 달라질 수 있으며, 이에 따라 가로와 세로 길이의 구하는 방식도 달라질 수 있습니다. 따라서 모든 경우에 대해 정확하게 처리하지 못할 수 있습니다.
