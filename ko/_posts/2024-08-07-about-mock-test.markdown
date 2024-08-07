---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Mock_Test
title: 모의고사 (with.Java)
# title: Mock test (with.Java)
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
date: 2024-08-07 09:00:00 +0900
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

## 모의고사 (with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

수포자는 수학을 포기한 사람의 준말입니다.

수포자 삼인방은 모의고사에 수학 문제를 전부 찍으려 합니다.

수포자는 1번 문제부터 마지막 문제까지 다음과 같이 찍습니다.

- 1번 수포자가 찍는 방식: 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, ...
- 2번 수포자가 찍는 방식: 2, 1, 2, 3, 2, 4, 2, 5, 2, 1, 2, 3, 2, 4, 2, 5, ...
- 3번 수포자가 찍는 방식: 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, ...

1번 문제부터 마지막 문제까지의 정답이 순서대로 들은 배열 answers가 주어졌을 때, 가장 많은 문제를 맞힌 사람이 누구인지 배열에 담아 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- 시험은 최대 10,000 문제로 구성되어있습니다.
- 문제의 정답은 1, 2, 3, 4, 5중 하나입니다.
- 가장 높은 점수를 받은 사람이 여럿일 경우, return하는 값을 오름차순 정렬해주세요.

#### 입출력 예시

| answers     | return  |
| ----------- | ------- |
| [1,2,3,4,5] | [1]     |
| [1,3,2,4,2] | [1,2,3] |

### 문제에 대한 나의 풀이

```java
import java.util.ArrayList;

class Solution {
    public int[] solution(int[] answers) {

        int[] person1 = {1, 2, 3, 4, 5};
        int[] person2 = {2, 1, 2, 3, 2, 4, 2, 5};
        int[] person3 = {3, 3, 1, 1, 2, 2, 4, 4, 5, 5};
        ArrayList<Integer> arr = new ArrayList<>();
        int[] count = new int[3];

        for(int i = 0; i < answers.length; i++){
            if(person1[i % person1.length] == answers[i]){
                count[0]++;
            }
            if(person2[i % person2.length] == answers[i]){
                count[1]++;
            }
            if(person3[i % person3.length] == answers[i]){
                count[2]++;
            }
        }

        int maxNum = Math.max(count[0], Math.max(count[1], count[2]));

        for(int i = 0; i < count.length; i++){
            if(maxNum == count[i]){
                arr.add(i + 1);
            }
        }

        int[] answer = new int[arr.size()];
        for(int i = 0; i < arr.size(); i++){
            answer[i] = arr.get(i);
        }
        return answer;
    }
}
```

### 풀이 설명

- solution 메서드는 정수 배열 answers를 입력으로 받습니다.
- 세 수포자의 찍기 패턴을 각각 person1, person2, person3 배열에 저장합니다.
- 각 수포자가 맞힌 문제의 수를 저장할 배열 count를 생성합니다. 크기는 3입니다.
- for 루프를 사용하여 정답 배열을 순회하며 각 수포자의 패턴과 비교하여 맞힌 문제의 수를 카운트합니다.
- 각 수포자가 맞힌 문제의 수 중 최대값을 구합니다.
- 최대값과 같은 값을 가지는 수포자의 번호를 arr 리스트에 저장합니다.
- arr 리스트의 내용을 배열로 변환하여 반환합니다.

### 결론

이 코드는 각 수포자의 찍기 패턴에 따라 정답과 비교하여 가장 많이 맞힌 사람을 찾는 문제를 해결합니다.
