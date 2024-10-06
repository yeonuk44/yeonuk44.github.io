---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Integer_Triangle
title: 정수 삼각형 (with.Java)
# title: Integer triangle (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, dp]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-06 09:00:00 +0900
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

## 정수 삼각형 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

위와 같은 삼각형의 꼭대기에서 바닥까지 이어지는 경로 중, 거쳐간 숫자의 합이 가장 큰 경우를 찾아보려고 합니다.

아래 칸으로 이동할 때는 대각선 방향으로 한 칸 오른쪽 또는 왼쪽으로만 이동 가능합니다.

예를 들어 3에서는 그 아래칸의 8 또는 1로만 이동이 가능합니다.

삼각형의 정보가 담긴 배열 triangle이 매개변수로 주어질 때, 거쳐간 숫자의 최댓값을 return 하도록 solution 함수를 완성하세요

#### 제한사항

- 삼각형의 높이는 1 이상 500 이하입니다.
- 삼각형을 이루고 있는 숫자는 0 이상 9,999 이하의 정수입니다.

#### 입출력 예

| triangle                                                | result |
| ------------------------------------------------------- | ------ |
| [[7], [3, 8], [8, 1, 0], [2, 7, 4, 4], [4, 5, 2, 6, 5]] | 30     |

### 문제 풀이

```java
class Solution {
    public int solution(int[][] triangle) {
        int answer = 0;

        for(int i = 1; i < triangle.length; i++){
            for(int j = 0; j < triangle[i].length; j++){
                // 왼쪽 계산
                if(j == 0){
                    triangle[i][j] += triangle[i - 1][j];
                }
                // 오른쪽 계산
                // 1 1 = 0 0
                else if(j == i){
                    triangle[i][j] += triangle[i - 1][j - 1];
                }
                // 중앙 계산
                else{
                    // 2 1 = 1 0 | 1 1
                    // 3 1 = 2 0 | 2 1
                    triangle[i][j] += Math.max(triangle[i - 1][j - 1], triangle[i - 1][j]);
                }
            }
        }

        int len = triangle.length;
        for(int i = 0; i < len; i++){
            if(answer < triangle[len - 1][i]){
                answer = triangle[len - 1][i];
            }
        }

        return answer;
    }
}
```

#### 풀이 설명

이 문제는 주어진 삼각형 배열에서 경로의 합이 최대가 되는 값을 찾아 반환하는 문제입니다.

동적 계획법을 사용하여 해결합니다.

먼저, 변수 answer를 초기화합니다.

이 변수는 최종적으로 반환할 최대 합을 저장합니다.

이제 삼각형 배열을 업데이트하기 위해 이중 for 루프를 사용합니다.

첫 번째 for 루프는 삼각형의 두 번째 행부터 마지막 행까지 순회합니다.

두 번째 for 루프는 현재 행의 모든 열을 순회합니다.

각 위치에서의 최대 경로 합을 계산하는 방법은 다음과 같습니다.

먼저, 왼쪽 계산입니다. 현재 위치가 행의 첫 번째 요소인 경우 바로 위의 요소를 더합니다.

다음으로 오른쪽 계산입니다. 현재 위치가 행의 마지막 요소인 경우 위의 대각선 왼쪽 요소를 더합니다.

마지막으로 중앙 계산입니다. 현재 위치가 행의 중간에 있는 경우 위의 두 대각선 요소 중 큰 값을 더합니다.

이제 마지막 행에서 최대 값을 찾아야 합니다.

마지막 행의 모든 요소를 순회하며 최대 값을 찾습니다. 그리고 이 최대 값을 반환합니다.

동적 계획법을 사용하여 삼각형 배열에서 최대 경로 합을 구할 수 있습니다.
