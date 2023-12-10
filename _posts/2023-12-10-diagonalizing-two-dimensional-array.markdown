---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Diagonalizing_Two_Dimensional_Array
title: Diagonalizing a Two-Dimensional Array (with.Java)
# title: Diagonalizing a Two-Dimensional Array (with.Java)
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
date: 2023-12-10 09:00:00 +0900
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

## "정사각형으로 만들기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

이차원 정수 배열 arr이 매개변수로 주어집니다.

arr의 행의 수가 더 많다면 열의 수가 행의 수와 같아지도록 각 행의 끝에 0을 추가하고, 열의 수가 더 많다면 행의 수가 열의 수와 같아지도록 각 열의 끝에 0을 추가한 이차원 배열을 return 하는 solution 함수를 작성해 주세요.

#### 입출력 예시

| arr                                                              | result                                                                       |
| ---------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [[572, 22, 37], [287, 726, 384], [85, 137, 292], [487, 13, 876]] | [[572, 22, 37, 0], [287, 726, 384, 0], [85, 137, 292, 0], [487, 13, 876, 0]] |

### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int[][] solution(int[][] arr) {
        int numRows = arr.length;
        int numCols = arr[0].length;

        if (numRows < numCols) {
            int[][] result = new int[numCols][numCols];
            for (int i = 0; i < numRows; i++) {
                result[i] = Arrays.copyOf(arr[i], numCols);
            }
            for (int i = numRows; i < numCols; i++) {
                result[i] = new int[numCols];
            }
            return result;
        }
        else if (numCols < numRows) {
            int[][] result = new int[numRows][numRows];
            for (int i = 0; i < numRows; i++) {
                result[i] = Arrays.copyOf(arr[i], numRows);
            }
            return result;
        }

        return arr;
    }
}
```

#### 풀이 설명

int numRows = arr.length;와 int numCols = arr[0].length;: 배열의 행과 열 수를 계산합니다.

if (numRows < numCols) : 만약 행 수가 열 수보다 작은 경우 (행이 더 적은 경우):

int[][] result = new int[numCols][numCols];: 새로운 정사각형 배열 result를 생성합니다.

for (int i = 0; i < numRows; i++) : 기존 배열의 행을 복사합니다. 배열 arr의 행을 result의 행으로 복사하며, 남는 열은 0으로 초기화됩니다.

for (int i = numRows; i < numCols; i++) : 남은 열에 대해서는 새로운 배열을 생성하여 초기화합니다.

else if (numCols < numRows) : 만약 열 수가 행 수보다 작은 경우 (열이 더 적은 경우):

int[][] result = new int[numRows][numRows];: 새로운 정사각형 배열 result를 생성합니다.

for (int i = 0; i < numRows; i++) : 기존 배열의 행을 복사합니다. 배열 arr의 행을 result의 행으로 복사합니다.

return arr;: 만약 arr이 이미 정사각형 모양이라면, 원래 배열 arr을 그대로 반환합니다.
