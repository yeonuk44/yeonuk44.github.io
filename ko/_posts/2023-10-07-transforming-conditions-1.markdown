---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Transforming_conditions_1
title: 조건에 맞게 수열 변환하기 1, 조건에 따른 배열 제어하는 방법에 대하여(with.Java)
# title: Transforming a sequence based on conditions 1, How to control an array based on conditions (with.Java)

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
date: 2023-10-07 09:00:00 +0900
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

### 수열과 구간 쿼리에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr와 2차원 정수 배열 queries이 주어집니다.

queries의 원소는 각각 하나의 query를 나타내며, [s, e] 꼴입니다.

각 query마다 순서대로 s ≤ i ≤ e인 모든 i에 대해 arr[i]에 1을 더합니다.

위 규칙에 따라 queries를 처리한 이후의 arr를 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| arr             | queries                | result          |
| --------------- | ---------------------- | --------------- |
| [0, 1, 2, 3, 4] | [[0, 1],[1, 2],[2, 3]] | [1, 3, 4, 4, 4] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] arr, int[][] queries) {
        int[] answer = arr;
        int idx = 0;
        for(int i = 0; i < queries.length; i++){
            for(int j = queries[i][0]; j <= queries[i][1]; j++){
                answer[j] += 1;
            }
        }
        return answer;
    }
}
```

##### 풀이 설명

int[] answer = arr;: 결과 배열 answer를 arr로 초기화합니다. 이렇게 하면 answer는 arr과 같은 배열을 가리키게 됩니다.

for(int i = 0; i < queries.length; i++) : queries 배열을 반복하면서 각 쿼리를 처리합니다.

for(int j = queries[i][0]; j <= queries[i][1]; j++) : 각 쿼리에 대한 범위를 반복하면서 해당 범위 내의 answer 배열 요소를 1씩 증가시킵니다.

return answer;: 모든 쿼리를 처리한 후, 변경된 answer 배열을 반환합니다.

이 코드는 queries 배열에 있는 범위에 해당하는 arr의 요소를 1씩 증가시키는 작업을 수행합니다.

하지만 주의할 점은 answer 배열이 arr 배열을 참조하므로, 이 작업은 arr 배열에도 영향을 미칩니다.

따라서 arr 배열을 변경하지 않고 새로운 배열에 결과를 저장하려면 새로운 배열을 생성하고 그 배열을 변경해야 합니다.
