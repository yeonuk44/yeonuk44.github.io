---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sequence_With_An_Interval_Query_1
title: 구간 쿼리를 통해 수열을 제어하는 방법에 대하여 1(with.Java)
# title: About browser

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
date: 2023-08-28 09:00:00 +0900
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

### 구간 쿼리를 통해 수열을 제어하는 방법에 대하여 1(with.Java)

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.
문제에 대해 먼저 알아보겠습니다.

#### 문제

정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [s, e, k] 꼴입니다.

각 query마다 순서대로 s ≤ i ≤ e인 모든 i에 대해 k보다 크면서 가장 작은 arr[i]를 찾습니다.

각 쿼리의 순서에 맞게 답을 저장한 배열을 반환하는 solution 함수를 완성해 주세요.
단, 특정 쿼리의 답이 존재하지 않으면 -1을 저장합니다.

**주의** 잘못 이해한다면 값을 비교하는 문제로 오해할 수 있습니다. 핵심은 s와 e **index** 범위에 대해 k보다 큰 수를 찾고, 해당되는 모든 수 중 가장 작은 수를 배열에 저장하면 풀리는 문제입니다. 오해 없으시길 바랍니다.

##### 입출력 예시

arr: [0, 1, 2, 4, 3]
queries: [[0, 4, 2],[0, 3, 2],[0, 2, 2]]
result: [3, 4, -1]

첫 번째 쿼리의 범위에는 0, 1, 2, 4, 3이 있으며 이 중 2보다 크면서 가장 작은 값은 3입니다.
두 번째 쿼리의 범위에는 0, 1, 2, 4가 있으며 이 중 2보다 크면서 가장 작은 값은 4입니다.
세 번째 쿼리의 범위에는 0, 1, 2가 있으며 여기에는 2보다 큰 값이 없습니다.
따라서 [3, 4, -1]을 return 합니다.

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

작성한 코드에 대해 왜 이렇게 작성했는지 최대한 기술해보겠습니다.
우선 결과를 저장할 int[] 타입의 result을 선언하고 배열의 크기는 queries의 요소의 길이만큼 필요할태니 queries.length를 입력해줍니다.
이후 순회 반복문을 선언하여 queries를 한바퀴 돌려줍니다. 그 과정에서 계산 값을 저장할 임시 ArrayList 타입인 temp를 선언해줍니다.
가장 작은 수를 비교하기 위한 int타입의 compare 변수도 선언해줍니다.
compare 변수 선언의 목적은 가장 작은 수를 저장하기 위함이기 때문에 초기 값으로 데이터 타입의 최대값을 나타내는 상수인 Integer.MAX_VALUE를 지정해줍니다.
이후 queries의 지정된 범위 값인 s<=i<=e 범위에 해당하는 인덱스를 추출하기 위한 반복문을 입력해줍니다.
이 반복문에서 우리는 queries에 지정된 k보다 큰 수를 아까 임시 저장 공간으로 쓰려고 선언한 temp에 저장해줍니다.
조건에 해당되는 값들을 다 저장하고 난 뒤, 해당되는 값이 없다면 -1을 반환하라는 조건이 있었기 때문에 ArrayList.isEmpty() 함수를 통해 값이 비어있다면 -1을 반환하게 예외처리를 해주고 값이 존재한다면 모든 조건을 만족하는 수들의 수만큼 순회하는 반복문을 작성합니다.
이후 차례대로 compare보다 작으면 compare에 해당 값을 저장하는 방식으로 가장 작은 수를 판별했습니다. 이후엔 compare에 있는 값을 result에 저장해주면 됩니다.
