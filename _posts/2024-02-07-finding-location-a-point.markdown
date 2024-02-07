---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_Location_A_Point
title: Finding the location of a point (with.Java)
# title: Finding the location of a point (with.Java)
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
date: 2024-02-07 09:00:00 +0900
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

## "2차원으로 만들기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 배열 num_list와 정수 n이 매개변수로 주어집니다.

num_list를 다음 설명과 같이 2차원 배열로 바꿔 return하도록 solution 함수를 완성해주세요.

num_list가 [1, 2, 3, 4, 5, 6, 7, 8] 로 길이가 8이고 n이 2이므로 num_list를 2 \* 4 배열로 다음과 같이 변경합니다.

2차원으로 바꿀 때에는 num_list의 원소들을 앞에서부터 n개씩 나눠 2차원 배열로 변경합니다.

#### 제한사항

- num_list의 길이는 n의 배 수개입니다.
- 0 ≤ num_list의 길이 ≤ 150
- 2 ≤ n < num_list의 길이

#### 입출력 예시

| num_list                           | n   | result                                   |
| ---------------------------------- | --- | ---------------------------------------- |
| [1, 2, 3, 4, 5, 6, 7, 8]           | 2   | [[1, 2], [3, 4], [5, 6], [7, 8]]         |
| [100, 95, 2, 4, 5, 6, 18, 33, 948] | 3   | [[100, 95, 2], [4, 5, 6], [18, 33, 948]] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[][] solution(int[] num_list, int n) {
        int[][] answer = new int[num_list.length / n][n];
        int temp = 0;
        for(int i = 0; i < num_list.length / n; i++){
            for(int j = 0; j < n; j++){
                answer[i][j] = num_list[temp++];
            }
        }
        return answer;
    }
}
```

### 풀이 설명

**주요 로직**

answer 배열의 크기를 num_list.length / n 행과 n 열로 정의합니다.

이중 반복문을 사용하여 1차원 배열의 원소를 2차원 배열로 옮깁니다.

**함수 설명**

특별한 함수를 사용하지 않고 직접 배열을 초기화하고 값을 할당하는 방식을 사용했습니다.

**개선 방향**

입력값이나 상황에 따라 마지막 행을 채우거나 무시하는 방식을 선택할 수 있는 선택지를 추가하는 것이 좋을 수 있습니다.

예외 처리를 통해 num_list의 크기와 n의 조건을 검사하여 적절한 처리를 할 수 있도록 코드를 보완할 수 있습니다.
