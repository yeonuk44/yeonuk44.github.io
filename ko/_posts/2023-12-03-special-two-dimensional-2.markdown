---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Special_Two_Dimensional_Array_2
title: 특별한 이차원 배열 2(with.Java)
# title: Special two-dimensional array 1 (with.Java)
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
date: 2023-12-03 09:00:00 +0900
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

## "특별한 이차원 배열 1" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 n이 매개변수로 주어질 때, 다음과 같은 n × n 크기의 이차원 배열 arr를 return 하는 solution 함수를 작성해 주세요.

arr[i][j] (0 ≤ i, j < n)의 값은 i = j라면 1, 아니라면 0입니다.

#### 입출력 예시

| n   | result                                                                                                                   |
| --- | ------------------------------------------------------------------------------------------------------------------------ |
| 3   | [[1, 0, 0], [0, 1, 0], [0, 0, 1]]                                                                                        |
| 6   | [[1, 0, 0, 0, 0, 0], [0, 1, 0, 0, 0, 0], [0, 0, 1, 0, 0, 0], [0, 0, 0, 1, 0, 0], [0, 0, 0, 0, 1, 0], [0, 0, 0, 0, 0, 1]] |
| 1   | [[1]]                                                                                                                    |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[][] solution(int n) {
        int[][] answer = new int[n][n];
        for(int i = 0; i < n; i++){
            for(int j = 0; j < n; j++){
                if(i == j){
                    answer[i][j] = 1;
                }else {
                    answer[i][j] = 0;
                }
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

int[][] answer = new int[n][n];: n x n 크기의 2차원 배열 answer를 생성합니다.

for(int i = 0; i < n; i++) : 배열의 행을 반복하면서 i값은 현재 행을 나타냅니다.

for(int j = 0; j < n; j++) : 배열의 열을 반복하면서 j값은 현재 열을 나타냅니다.

if(i == j) : 만약 현재 행과 열의 인덱스가 같다면 (주대각선 요소):

해당 위치의 배열 요소에 1을 저장합니다.

else : 그 외의 경우 (주대각선 요소가 아닌 경우):

해당 위치의 배열 요소에 0을 저장합니다.

return answer;: 단위 행렬로 초기화된 2차원 배열 answer를 반환합니다.
