---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Convert_String_To_Integer
title: 문자열을 정수로 변환하기(with.Java)
# title: Convert a string to an integer (with.Java)
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
date: 2023-11-10 09:00:00 +0900
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

### "전국 대회 선발 고사" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

0번부터 n - 1번까지 n명의 학생 중 3명을 선발하는 전국 대회 선발 고사를 보았습니다.

등수가 높은 3명을 선발해야 하지만, 개인 사정으로 전국 대회에 참여하지 못하는 학생들이 있어 참여가 가능한 학생 중 등수가 높은 3명을 선발하기로 했습니다.

각 학생들의 선발 고사 등수를 담은 정수 배열 rank와 전국 대회 참여 가능 여부가 담긴 boolean 배열 attendance가 매개변수로 주어집니다.

전국 대회에 선발된 학생 번호들을 등수가 높은 순서대로 각각 a, b, c번이라고 할 때 10000 × a + 100 × b + c를 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| rank                  | attendance                                    | result |
| --------------------- | --------------------------------------------- | ------ |
| [3, 7, 2, 5, 4, 6, 1] | [false, true, true, true, true, false, false] | 20403  |
| [1, 2, 3]             | [true, true, true]                            | 102    |
| [6, 1, 5, 2, 3, 4]    | [true, false, true, false, false, true]       | 50200  |

#### 문제에 대한 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public int solution(int[] rank, boolean[] attendance) {
        int answer = 0;
        int length = rank.length;
        int[][] students = new int[length][2];

        for (int i = 0; i < length; i++) {
            students[i][0] = rank[i];
            students[i][1] = attendance[i] ? 1 : 0;
        }

        Arrays.sort(students, (a, b) -> Integer.compare(a[0], b[0]));

        int count = 0;
        int[] selected = new int[3];

        for (int i = 0; i < length; i++) {
            if (count == 3) {
                break;
            }
            if (students[i][1] == 1) {
                selected[count++] = students[i][0];

            }

        }

        for (int i = 0; i < length; i++) {
            for (int j = 0; j < 3; j++) {
                if (rank[i] == selected[j]) {
                    switch (j) {
                        case 0:
                            answer += 10000 * i;
                            break;
                        case 1:
                            answer += 100 * i;
                            break;
                        case 2:
                            answer += i;
                            break;
                        default:
                            break;
                    }
                }
            }
        }

        return answer;
    }
}
```

##### 풀이 설명

int length = rank.length;: 입력 배열의 길이를 length 변수에 저장합니다.

int[][] students = new int[length][2];: 각 학생의 등수와 출석 여부를 저장할 이차원 배열 students를 생성합니다.

배열의 각 행은 학생을 나타내며, 첫 번째 열에는 등수를, 두 번째 열에는 출석 여부를 저장합니다.

Arrays.sort(students, (a, b) -> Integer.compare(a[0], b[0]));: 학생들을 등수에 따라 오름차순으로 정렬합니다.

이로써 등수가 낮은 학생부터 정렬됩니다.

int count = 0;, int[] selected = new int[3];: 등수가 높은 상위 3명의 학생을 선택하기 위한 변수 count와 배열 selected를 초기화합니다.

루프를 통해 등수가 높은 상위 3명의 학생을 선택합니다. students 배열에서 출석한 학생을 선택하고 selected 배열에 등수를 저장합니다.

다시 한 번 루프를 통해 학생의 등수에 따라 점수를 계산합니다.

상위 3명의 학생에게는 1등부터 3등까지 10,000, 100, 1의 가중치가 부여되며, 이를 이용하여 각 학생의 점수를 계산합니다.

answer 변수에 각 학생의 점수를 더한 후, 최종적으로 answer 값을 반환합니다.

이 코드는 학생들의 등수와 출석 여부를 기반으로 학생들을 정렬하고 상위 3명의 학생에게 가중치를 부여하여 점수를 계산하는 작업을 수행합니다.

반환되는 점수는 각 학생의 등수와 출석 여부에 따라 결정됩니다.
