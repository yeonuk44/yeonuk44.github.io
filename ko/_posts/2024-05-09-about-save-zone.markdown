---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Save_Zone
title: 안전지대 (with.Java)
# title: Safe zone (with.Java)
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
date: 2024-05-09 09:00:00 +0900
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

## "안전지대 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

지뢰가 있는 지역과 지뢰에 인접한 위, 아래, 좌, 우 대각선 칸을 모두 위험지역으로 분류합니다.

지뢰는 2차원 배열 board에 1로 표시되어 있고 board에는 지뢰가 매설 된 지역 1과, 지뢰가 없는 지역 0만 존재합니다.

지뢰가 매설된 지역의 지도 board가 매개변수로 주어질 때, 안전한 지역의 칸 수를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- board는 n x n 배열입니다.
- 1 ≤ n ≤ 100
- 지뢰는 1로 표시되어 있습니다.
- board에는 지뢰가 있는 지역 1과 지뢰가 없는 지역 0만 존재합니다.

#### 입출력 예시

<!-- | keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] | -->

| my_string                                                                                                                | result |
| ------------------------------------------------------------------------------------------------------------------------ | ------ |
| [[0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 1, 0, 0], [0, 0, 0, 0, 0]]                                    | 16     |
| [[0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 1, 1, 0], [0, 0, 0, 0, 0]]                                    | 13     |
| [[1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1]] | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[][] board) {
        int[][] secondArr = new int[board.length+2][board.length+2];
        int answer = 0;
        for(int i = 0; i < board.length; i++){
            for(int j = 0; j < board.length; j++){
                if(board[i][j] == 1){
                    for(int a = i; a <= i+2; a++){
                        for(int b = j; b <= j+2; b++){
                            if(secondArr[a][b] != 1){
                                secondArr[a][b] = 1;
                            }
                        }
                    }
                }
            }
        }
        for(int i = 1; i < secondArr.length - 1; i++){
            for(int j = 1; j < secondArr.length-1; j++){
                if(secondArr[i][j] == 0){
                    answer++;
                }
            }
        }
        return answer;
    }
}
```

### 풀이 설명

- 새로운 2차원 배열 생성: 기존의 보드 배열보다 크기가 1씩 큰 새로운 2차원 배열 secondArr를 생성합니다. 이는 보드의 경계 부분을 처리하기 위함입니다.
- 보드 탐색 및 주변 셀 갱신: 기존의 보드를 탐색하면서 값이 1인 셀을 찾으면, 해당 셀을 중심으로 주변 8개의 셀을 모두 2로 갱신합니다.
- 새로운 배열 탐색 및 0인 셀 개수 세기: 새로운 배열을 탐색하면서 값이 0인 셀의 개수를 세어 answer 변수에 저장합니다.
- 결과 반환: 최종적으로 세어진 0인 셀의 개수를 반환합니다.

**코드 장단점**

- 장점: 0인 셀의 개수를 효율적으로 세는 방법을 사용하여 코드가 간결합니다. 보드의 경계 부분을 추가적인 처리 없이 쉽게 다룰 수 있습니다.
- 단점: 이 코드는 보드의 모든 셀을 한 번씩 더 탐색하여 처리하므로 실행 시간이 비효율적일 수 있습니다. 특히 보드의 크기가 클 경우에는 성능에 영향을 줄 수 있습니다.
