---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Spiralizing_Integers
title: 정수를 나선형으로 배치하기(with.Java)
# title: Spiralizing integers (with.Java)
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
date: 2023-12-05 09:00:00 +0900
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

## "정수를 나선형으로 배치하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

양의 정수 n이 매개변수로 주어집니다.

n × n 배열에 1부터 n2 까지 정수를 인덱스 [0][0]부터 시계방향 나선형으로 배치한 이차원 배열을 return 하는 solution 함수를 작성해 주세요.

#### 입출력 예시

| n   | result                                                                                                |
| --- | ----------------------------------------------------------------------------------------------------- |
| 4   | [[1, 2, 3, 4], [12, 13, 14, 5], [11, 16, 15, 6], [10, 9, 8, 7]]                                       |
| 5   | [[1, 2, 3, 4, 5], [16, 17, 18, 19, 6], [15, 24, 25, 20, 7], [14, 23, 22, 21, 8], [13, 12, 11, 10, 9]] |

### 문제에 대한 나의 풀이

```java
public class Solution {
    public int[][] solution(int n) {
        int[][] result = new int[n][n];

        int num = 1;
        int rowStart = 0, rowEnd = n - 1;
        int colStart = 0, colEnd = n - 1;

        while (num <= n * n) {
            for (int i = colStart; i <= colEnd; i++) {
                result[rowStart][i] = num++;
            }
            rowStart++;
            for (int i = rowStart; i <= rowEnd; i++) {
                result[i][colEnd] = num++;
            }
            colEnd--;
            for (int i = colEnd; i >= colStart; i--) {
                result[rowEnd][i] = num++;
            }
            rowEnd--;
            for (int i = rowEnd; i >= rowStart; i--) {
                result[i][colStart] = num++;
            }
            colStart++;
        }

        return result;
    }
}
```

#### 풀이 설명

int[][] result = new int[n][n];: n x n 크기의 2차원 배열 result를 생성합니다.

int num = 1;: 숫자를 초기화합니다.

int rowStart = 0, rowEnd = n - 1;와 int colStart = 0, colEnd = n - 1;: 행과 열의 시작과 끝 인덱스를 초기화합니다.

while (num <= n \* n) : 숫자 num이 n x n보다 작거나 같은 동안 반복합니다.

for (int i = colStart; i <= colEnd; i++) : 현재 행렬의 윗 행에서 좌에서 우로 이동하며 숫자를 채웁니다.

result[rowStart][i]에 num을 저장하고 num을 증가시킵니다.

rowStart++;: 윗 행을 다 채우고 나면 다음 행으로 이동합니다.

이제 오른쪽 열에서 위에서 아래로 이동하며 숫자를 채우고, 그 다음 왼쪽 행에서 우측에서 좌측으로 이동하며 숫자를 채우고, 아랫 행에서 위에서 아래로 이동하며 숫자를 채웁니다.

각 단계에서 num이 1씩 증가하고 행과 열의 시작과 끝 인덱스가 조절됩니다.

return result;: 모든 요소가 숫자로 채워진 2차원 배열 result를 반환합니다.

이 코드는 효율적인 스파이럴 패턴을 사용하여 2차원 배열을 생성하고 1부터 n x n까지의 숫자로 채웁니다.
