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

## "특별한 이차원 배열 2" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

n × n 크기의 이차원 배열 arr이 매개변수로 주어질 때, arr이 다음을 만족하면 1을 아니라면 0을 return 하는 solution 함수를 작성해 주세요.

0 ≤ i, j < n인 정수 i, j에 대하여 arr[i][j] = arr[j][i]

#### 입출력 예시

| arr                                                                               | result |
| --------------------------------------------------------------------------------- | ------ |
| [[5, 192, 33], [192, 72, 95], [33, 95, 999]]                                      | 1      |
| [[19, 498, 258, 587], [63, 93, 7, 754], [258, 7, 1000, 723], [587, 754, 723, 81]] | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[][] arr) {
        int answer = 0;
        for(int i = 0; i < arr.length - 1; i++){
            for(int j = 0; j < arr.length; j++){
                if(arr[i][j] != arr[j][i]){
                    return answer;
                }
            }
        }
        answer = 1;
        return answer;
    }
}

```

#### 풀이 설명

int answer = 0;: 결과 값을 저장할 변수 answer를 초기화합니다.

for(int i = 0; i < arr.length - 1; i++) : 2차원 배열을 반복하며 주대각선을 기준으로 위쪽 절반만 확인합니다. (arr.length는 배열의 크기입니다.)

for(int j = 0; j < arr.length; j++) : 현재 행 i와 열 j에 대한 원소와 열 i와 행 j에 대한 원소를 비교하여 대칭 여부를 확인합니다.

if(arr[i][j] != arr[j][i]) : 만약 현재 원소와 대칭 위치의 원소가 다르다면 (대칭이 아닌 경우):

answer를 0으로 설정하고, 함수를 종료합니다.

answer = 1;: 모든 원소가 대칭인 경우, answer를 1로 설정합니다.

return answer;: 결과인 answer 값을 반환합니다.
