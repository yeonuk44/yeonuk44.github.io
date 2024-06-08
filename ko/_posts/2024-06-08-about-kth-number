---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Kth_Number
title: K번째수 (with.Java)
# title: Kth number (with.Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, sort]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-06-08 09:00:00 +0900
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

## "K번째수 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

배열 array의 i번째 숫자부터 j번째 숫자까지 자르고 정렬했을 때, k번째에 있는 수를 구하려 합니다.

예를 들어 array가 [1, 5, 2, 6, 3, 7, 4], i = 2, j = 5, k = 3이라면

array의 2번째부터 5번째까지 자르면 [5, 2, 6, 3]입니다.

1에서 나온 배열을 정렬하면 [2, 3, 5, 6]입니다.

2에서 나온 배열의 3번째 숫자는 5입니다.

배열 array, [i, j, k]를 원소로 가진 2차원 배열 commands가 매개변수로 주어질 때, commands의 모든 원소에 대해 앞서 설명한 연산을 적용했을 때 나온 결과를 배열에 담아 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- array의 길이는 1 이상 100 이하입니다.
- array의 각 원소는 1 이상 100 이하입니다.
- commands의 길이는 1 이상 50 이하입니다.
- commands의 각 원소는 길이가 3입니다.

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| array                 | commands                          | return    |
| --------------------- | --------------------------------- | --------- |
| [1, 5, 2, 6, 3, 7, 4] | [[2, 5, 3], [4, 4, 1], [1, 7, 3]] | [5, 6, 3] |

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];
        for(int i = 0; i < commands.length; i++){
            int[] tempArr = Arrays.copyOfRange(array, commands[i][0] - 1, commands[i][1]);
            Arrays.sort(tempArr);
            answer[i] = tempArr[commands[i][2] - 1];
        }
        return answer;
    }
}
```

### 풀이 리뷰

solution 메서드는 정수 배열 array와 2차원 정수 배열 commands를 입력으로 받습니다.

결과를 저장할 정수 배열 answer를 생성합니다. commands 배열의 크기와 동일한 크기로 설정됩니다.

commands 배열을 순회하면서 각 명령어에 대해 처리를 진행합니다.

각 명령어는 배열을 특정 구간으로 자르고, 그 구간을 정렬한 후에 특정 위치의 값을 추출하는 것입니다.

Arrays.copyOfRange() 메서드를 사용하여 주어진 배열에서 해당하는 구간을 복사하여 새로운 배열을 생성합니다.

복사한 배열을 Arrays.sort() 메서드를 사용하여 정렬합니다.

정렬된 배열에서 commands[i][2] - 1 위치에 있는 값을 answer[i]에 저장합니다. 주의할 점은 배열의 인덱스는 0부터 시작하므로 명령어의 위치 값에서 1을 빼줘야 합니다.

모든 명령어에 대한 처리가 끝나면 answer 배열을 반환합니다.

이 코드는 각 명령어에 따라 배열을 잘라내고 정렬한 후에 특정 위치의 값을 추출하여 반환하는 문제를 해결합니다.
