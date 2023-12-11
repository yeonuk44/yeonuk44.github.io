---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Access_Lines
title: About access lines
# title: About access lines
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Network
# multiple tag entries are possible
tags: [network]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-12-11 09:00:00 +0900
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

## "이차원 배열 대각선 순회하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

2차원 정수 배열 board와 정수 k가 주어집니다.

i + j <= k를 만족하는 모든 (i, j)에 대한 board[i][j]의 합을 return 하는 solution 함수를 완성해 주세요.

#### 입출력 예시

| board                                     | k   | result |
| ----------------------------------------- | --- | ------ |
| [[0, 1, 2],[1, 2, 3],[2, 3, 4],[3, 4, 5]] | 2   | 8      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[][] board, int k) {
        int answer = 0;
        for(int i = 0; i < board.length; i++){
            for(int j = 0; j < board[i].length; j++){
                if(i + j <= k){
                    answer += board[i][j];
                }
            }
        }
        return answer;
    }
}

```

#### 풀이 설명

int answer = 0;: 결과 값을 저장할 변수 answer를 초기화합니다.

중첩된 반복문을 사용하여 2차원 배열 board를 순회합니다. 외부 반복문은 행 (i), 내부 반복문은 열 (j)를 나타냅니다.

if(i + j <= k) : 현재 행과 열의 합인 i + j가 k 이하인 경우:

answer에 현재 위치의 원소 board[i][j]를 더합니다.

모든 원소를 확인한 후 answer 값을 반환합니다.

이 코드는 주어진 조건에 따라 2차원 배열에서 특정 조건을 만족하는 원소들의 합을 계산하는 알고리즘을 구현합니다.
