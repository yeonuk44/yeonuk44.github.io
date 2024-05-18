---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Ranking
title: Ranking (with. Java)
# title: Ranking (with. Java)
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
date: 2024-05-18 09:00:00 +0900
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

## "특이한 정렬 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 n을 기준으로 n과 가까운 수부터 정렬하려고 합니다.

이때 n으로부터의 거리가 같다면 더 큰 수를 앞에 오도록 배치합니다.

정수가 담긴 배열 numlist와 정수 n이 주어질 때 numlist의 원소를 n으로부터 가까운 순서대로 정렬한 배열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ n ≤ 10,000
- 1 ≤ numlist의 원소 ≤ 10,000
- 1 ≤ numlist의 길이 ≤ 100
- numlist는 중복된 원소를 갖지 않습니다.

#### 입출력 예시

<!-- | lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| numlist                       | n   | result                               |
| ----------------------------- | --- | ------------------------------------ |
| [1, 2, 3, 4, 5, 6]            | 4   | [4, 5, 3, 6, 2, 1]                   |
| [10000,20,36,47,40,6,10,7000] | 30  | [36, 40, 20, 47, 10, 6, 7000, 10000] |

### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int[] solution(int[] numlist, int n) {
        int[] answer = new int[numlist.length];
        int absValue = 0;
        int temp = Integer.MAX_VALUE;
        int idx = 0;
        Arrays.sort(numlist);

        ArrayList<Integer> arr_new = new ArrayList<Integer>();
        for (int i : numlist){
            arr_new.add(i);
        }


        for(int i = 0; i < answer.length; i++){
            for(int j = arr_new.size() - 1; j >= 0; j--){
                absValue = Math.abs(n - arr_new.get(j));
                if(temp > absValue){
                    temp = absValue;
                    idx = j;
                }
            }
            answer[i] = arr_new.get(idx);
            temp = Integer.MAX_VALUE;
            arr_new.remove(arr_new.get(idx));
        }
        return answer;
    }
}
```

### 풀이 설명

주어진 배열 numlist를 정렬합니다.

정답을 저장할 배열 answer를 초기화합니다.

배열 numlist의 각 요소를 저장하기 위한 ArrayList arr_new를 생성하고, 정렬된 numlist의 각 요소를 arr_new에 추가합니다.

n과 현재 요소와의 차이를 계산하여 absValue에 저장합니다.

만약 absValue가 현재까지의 최솟값 temp보다 작다면, temp를 absValue로 갱신하고, 현재 인덱스 idx를 해당 요소의 인덱스로 설정합니다.

temp와 idx를 사용하여 찾은 가장 가까운 숫자를 answer에 저장합니다.

arr_new에서 해당 숫자를 제거합니다.

반복이 완료되면 answer를 반환합니다.
