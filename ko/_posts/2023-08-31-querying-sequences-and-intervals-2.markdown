---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Querying_Sequences_and_Intervals_2
title: 수열과 구간 쿼리 2(with.Java)
# title: Querying Sequences and Intervals 2(with.Java)
# implementing arrays for given conditions

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
date: 2023-08-31 09:00:00 +0900
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

### 수열과 구간 쿼리(with.Java)에 대하여 알아본 글입니다.

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.
문제에 대해 먼저 알아보겠습니다.

#### 문제

정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [s, e, k] 꼴입니다.

각 query마다 순서대로 s ≤ i ≤ e인 모든 i에 대해 k보다 크면서 가장 작은 arr[i]를 찾습니다.

각 쿼리의 순서에 맞게 답을 저장한 배열을 반환하는 solution 함수를 완성해 주세요.
단, 특정 쿼리의 답이 존재하지 않으면 -1을 저장합니다.

##### 입출력 예시

arr: [0, 1, 2, 4, 3]
queries: [[0, 4, 2],[0, 3, 2],[0, 2, 2]]
result: [3, 4, -1]

첫 번째 쿼리의 범위에는 0, 1, 2, 4, 3이 있으며 이 중 2보다 크면서 가장 작은 값은 3입니다.
두 번째 쿼리의 범위에는 0, 1, 2, 4가 있으며 이 중 2보다 크면서 가장 작은 값은 4입니다.
세 번째 쿼리의 범위에는 0, 1, 2가 있으며 여기에는 2보다 큰 값이 없습니다.
따라서 [3, 4, -1]을 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr, int[][] queries) {
        int[] result = new int[queries.length];

        for(int i = 0; i < queries.length; i++){
            ArrayList<Integer> temp = new ArrayList<Integer>();
            int compare = Integer.MAX_VALUE;

            for(int j = queries[i][0]; j <= queries[i][1]; j++){
                if(arr[j] > queries[i][2]){
                    temp.add(arr[j]);
                }
            }

            if(temp.isEmpty()){
                result[i] = -1;
            } else {
                for(int k = 0; k < temp.size(); k++){
                    if(compare > temp.get(k)){
                        compare = temp.get(k);
                    }
                }
                result[i] = compare;
            }
        }



        return result;
        }
}
```

##### 풀이 설명

public int[] solution(int[] arr, int[][] queries): 두 개의 배열 arr과 queries를 입력으로 받아 문제를 해결하는 함수입니다. 결과로 정수 배열을 반환합니다.
int[] result = new int[queries.length];: 결과를 저장할 정수 배열 result를 queries 배열의 길이로 초기화합니다. 각 queries 요소에 대한 결과 값을 저장할 배열입니다.
for(int i = 0; i < queries.length; i++) { ... }: queries 배열의 각 요소에 대해서 반복문을 실행합니다.
ArrayList<Integer> temp = new ArrayList<Integer>();: 현재 쿼리에 대한 조건을 만족하는 arr 배열의 요소들을 저장할 임시 리스트 temp를 생성합니다.
int compare = Integer.MAX_VALUE;: 현재 쿼리에 대한 조건을 만족하는 값들 중 가장 작은 값을 찾기 위한 비교 변수 compare를 최대값으로 초기화합니다.
내부 반복문에서 queries[i][0]부터 queries[i][1]까지의 범위에 있는 arr 배열의 요소를 검사합니다.
if(arr[j] > queries[i][2]) { ... }: 현재 요소가 queries 배열의 조건 queries[i][2]보다 큰지 확인하여 큰 경우 temp 리스트에 추가합니다.
조건을 만족하는 값들이 없는 경우 temp 리스트가 비어있다면 result[i]에 -1을 저장합니다.
조건을 만족하는 값들이 있는 경우 temp 리스트 내에서 가장 작은 값을 찾아 compare와 비교하여 더 작은 값을 compare에 저장합니다.
마지막으로 compare에 저장된 값이 result[i]에 저장됩니다.
반복문이 끝나면 result 배열이 완성되어 반환됩니다.

즉, 이 코드는 주어진 배열 arr의 특정 범위와 조건에 맞는 값을 찾아 결과 배열에 저장하는 작업을 수행합니다.
