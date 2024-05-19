---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Babble_1
title: Babble 1 (with.Java)
# title: Babble 1 (with.Java)
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
date: 2024-05-19 09:00:00 +0900
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

## "등수 매기기 (with. Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

영어 점수와 수학 점수의 평균 점수를 기준으로 학생들의 등수를 매기려고 합니다.

영어 점수와 수학 점수를 담은 2차원 정수 배열 score가 주어질 때, 영어 점수와 수학 점수의 평균을 기준으로 매긴 등수를 담은 배열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 0 ≤ score[0], score[1] ≤ 100
- 1 ≤ score의 길이 ≤ 10
- score의 원소 길이는 2입니다.
- score는 중복된 원소를 갖지 않습니다.

#### 입출력 예시

<!-- | lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| score                                                                      | result                |
| -------------------------------------------------------------------------- | --------------------- |
| [[80, 70], [90, 50], [40, 70], [50, 80]]                                   | [1, 2, 4, 3]          |
| [[80, 70], [70, 80], [30, 50], [90, 100], [100, 90], [100, 100], [10, 30]] | [4, 4, 6, 2, 2, 1, 7] |

### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int[] solution(int[][] score) {
        int[] answer = new int[score.length];
        List<Integer> list = new ArrayList<>();

        for(int[] tempArray : score){
            list.add(tempArray[0] + tempArray[1]);
        }

        list.sort(Comparator.reverseOrder());

        for(int i = 0; i < score.length; i++){
            answer[i] = list.indexOf(score[i][0] + score[i][1]) + 1;
        }
        return answer;
    }
}
```

### 풀이 설명

solution 메서드는 2차원 정수 배열 score를 입력으로 받습니다.

이 배열은 각 학생의 영어 점수와 수학 점수를 나타냅니다.

먼저, 각 학생의 영어 점수와 수학 점수의 합계를 담을 리스트 list를 생성합니다.

배열 score를 순회하면서 각 학생의 영어 점수와 수학 점수를 합산하여 list에 추가합니다.

합산된 점수를 기준으로 내림차순으로 정렬합니다.

다시 한 번 배열 score를 순회하면서 각 학생의 합산된 점수가 몇 번째로 큰지 확인하여 등수를 결정합니다.

등수를 결정한 후, 해당 등수를 answer 배열에 저장합니다.

최종적으로 answer 배열을 반환합니다.

이 방식으로 학생들의 점수 합계를 기준으로 등수를 매긴 이유는 평균을 사용하면 소수점 문제가 발생할 수 있기 때문입니다.
