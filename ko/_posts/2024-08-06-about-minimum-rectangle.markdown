---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Minimum_Rectangle
title: 최소직사각형 (with.Java)
# title: Minimum rectangle (with.Java)
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
date: 2024-08-06 09:00:00 +0900
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

## 최소직사각형 (with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

명함 지갑을 만드는 회사에서 지갑의 크기를 정하려고 합니다.

다양한 모양과 크기의 명함들을 모두 수납할 수 있으면서, 작아서 들고 다니기 편한 지갑을 만들어야 합니다.

이러한 요건을 만족하는 지갑을 만들기 위해 디자인팀은 모든 명함의 가로 길이와 세로 길이를 조사했습니다.

아래 표는 4가지 명함의 가로 길이와 세로 길이를 나타냅니다.

| 명함번호 | 가로길이 | 세로길이 |
| -------- | -------- | -------- |
| 1        | 60       | 50       |
| 2        | 30       | 70       |
| 3        | 60       | 30       |
| 4        | 80       | 40       |

가장 긴 가로 길이와 세로 길이가 각각 80, 70이기 때문에 80(가로) x 70(세로) 크기의 지갑을 만들면 모든 명함들을 수납할 수 있습니다.

하지만 2번 명함을 가로로 눕혀 수납한다면 80(가로) x 50(세로) 크기의 지갑으로 모든 명함들을 수납할 수 있습니다.

이때의 지갑 크기는 4000(=80 x 50)입니다.

모든 명함의 가로 길이와 세로 길이를 나타내는 2차원 배열 sizes가 매개변수로 주어집니다.

모든 명함을 수납할 수 있는 가장 작은 지갑을 만들 때, 지갑의 크기를 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- sizes의 길이는 1 이상 10,000 이하입니다.
- sizes의 원소는 [w, h] 형식입니다.
- w는 명함의 가로 길이를 나타냅니다.
- h는 명함의 세로 길이를 나타냅니다.
- w와 h는 1 이상 1,000 이하인 자연수입니다.

#### 입출력 예시

| sizes                                         | result    |
| --------------------------------------------- | --------- | ------- | ------ |
| [[60, 50], [30, 70], [60, 30], [80, 40]]      | 4000      |
| [[10, 7], [12, 3], [8, 15], [14, 7], [5, 15]] | 120       |
| [[14, 4], [19, 6], [6, 16], [18, 7], [7, 11]] | 133       |
| <!--                                          | start_num | end_num | result |
| ---------                                     | -------   | ------  |
| 10                                            | 3         | 0       | -->    |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[][] sizes) {
        int answer = 0;
        int temp = 0;
        int maxRow = 0;
        int maxCol = 0;
        for(int i = 0; i < sizes.length; i++){
            temp = sizes[i][0];
            if(temp < sizes[i][1]){
                sizes[i][0] = sizes[i][1];
                sizes[i][1] = temp;
            }
            if(maxRow < sizes[i][0]){
                maxRow = sizes[i][0];
            }
            if(maxCol < sizes[i][1]){
                maxCol = sizes[i][1];
            }
        }
        answer = maxRow * maxCol;
        return answer;
    }
}
```

### 풀이 설명

- solution 메서드는 2차원 정수 배열 sizes를 입력으로 받습니다.
- 변수 answer를 초기화하고, 사각형을 가로로 배치할 때의 최대 가로 길이를 나타내는 변수 maxRow와 세로로 배치할 때의 최대 세로 길이를 나타내는 변수 maxCol을 초기화합니다.
- for 루프를 사용하여 각 사각형의 가로와 세로 길이를 순회합니다.
- 각 사각형에 대해 가로 길이와 세로 길이를 비교하여 가로가 세로보다 작다면 가로와 세로를 서로 교환합니다. 이는 가로가 항상 세로보다 크거나 같도록 만들기 위함입니다.
- 가로와 세로의 최대 길이를 갱신합니다. 이는 모든 사각형이 가로와 세로를 최대한 활용하여 배치되었을 때의 가로와 세로 길이를 의미합니다.
- 최종적으로 최대 가로 길이와 최대 세로 길이를 곱하여 answer에 저장합니다.
  answer를 반환합니다.

### 결론

이 코드는 각 사각형의 가로와 세로 길이를 고려하여 사각형을 최대한 넓게 배치할 수 있는 경우의 넓이를 구하는 문제를 해결합니다.
