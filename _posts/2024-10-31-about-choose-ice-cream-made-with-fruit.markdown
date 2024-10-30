---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Choose_Ice_Cream_Made_With_Fruit
title: Choose ice cream made with fruit (with.MySQL)
# title: Choose ice cream made with fruit (with.MySQL)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Sql
# multiple tag entries are possible
tags: [sql, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-31 09:00:00 +0900
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

## 과일로 만든 아이스크림 고르기 (with.MySQL) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

일렬로 나열된 n개의 풍선이 있습니다.

모든 풍선에는 서로 다른 숫자가 써져 있습니다.

당신은 다음 과정을 반복하면서 풍선들을 단 1개만 남을 때까지 계속 터트리려고 합니다.

임의의 인접한 두 풍선을 고른 뒤, 두 풍선 중 하나를 터트립니다.

터진 풍선으로 인해 풍선들 사이에 빈 공간이 생겼다면, 빈 공간이 없도록 풍선들을 중앙으로 밀착시킵니다.

여기서 조건이 있습니다.

인접한 두 풍선 중에서 번호가 더 작은 풍선을 터트리는 행위는 최대 1번만 할 수 있습니다.

즉, 어떤 시점에서 인접한 두 풍선 중 번호가 더 작은 풍선을 터트렸다면, 그 이후에는 인접한 두 풍선을 고른 뒤 번호가 더 큰 풍선만을 터트릴 수 있습니다.

당신은 어떤 풍선이 최후까지 남을 수 있는지 알아보고 싶습니다.

위에 서술된 조건대로 풍선을 터트리다 보면, 어떤 풍선은 최후까지 남을 수도 있지만, 어떤 풍선은 무슨 수를 쓰더라도 마지막까지 남기는 것이 불가능할 수도 있습니다.

일렬로 나열된 풍선들의 번호가 담긴 배열 a가 주어집니다.

위에 서술된 규칙대로 풍선들을 1개만 남을 때까지 터트렸을 때 최후까지 남기는 것이 가능한 풍선들의 개수를 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- a의 길이는 1 이상 1,000,000 이하입니다.
- a[i]는 i+1 번째 풍선에 써진 숫자를 의미합니다.
- a의 모든 수는 -1,000,000,000 이상 1,000,000,000 이하인 정수입니다.
- a의 모든 수는 서로 다릅니다.

#### 입출력 예

<!--
| Column name | Type         | Nullable |
| ----------- | ------------ | -------- |
| CAR_ID      | INTEGER      | FALSE    |
| CAR_TYPE    | VARCHAR(255) | FALSE    |
| DAILY_FEE   | INTEGER      | FALSE    |
| OPTIONS     | VARCHAR(255) | FALSE    | -->

| a                                     | result |
| ------------------------------------- | ------ |
| [9,-1,-5]                             | 3      |
| [-16,27,65,-2,58,-92,-71,-68,-61,-33] | 6      |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### 문제 풀이

```java
class Solution {
    public int solution(int[] a) {
        int answer = 2;
        int[] left_arr = new int[a.length];
        int[] right_arr = new int[a.length];
        int left_min = a[0];
        int right_min = a[a.length - 1];

        int idx = a.length - 2;
        for(int i = 1; i < a.length - 1; i++){
            if(left_min > a[i]){
                left_min = a[i];
            }
            if(right_min > a[idx]){
                right_min = a[idx];
            }
            left_arr[i] = left_min;
            right_arr[idx--] = right_min;
        }
        if(a.length == 1){
            return 1;
        }
        for(int i = 1; i < a.length - 1; i++){
            if(left_arr[i] < a[i] && right_arr[i] < a[i]){
                continue;
            }
            answer++;
        }
        return answer;
    }
}
```

#### 풀이 설명

이 코드는 주어진 배열 a에서 끝까지 남을 수 있는 요소의 개수를 계산하는 문제를 해결합니다.

배열의 첫 번째와 마지막 요소는 항상 끝까지 남을 수 있습니다.

따라서 초기 값으로 answer를 2로 설정합니다.

배열의 크기가 1인 경우 예외적으로 1을 반환합니다.

먼저, 왼쪽에서부터의 최소값을 저장하는 배열 left_arr와 오른쪽에서부터의 최소값을 저장하는 배열 right_arr를 만듭니다.

left_min은 배열의 첫 번째 요소로 초기화하고, right_min은 배열의 마지막 요소로 초기화합니다.

다음으로, 배열을 순회하면서 left_min과 right_min을 갱신합니다.

왼쪽부터 현재 요소까지의 최소값을 left_arr에 저장하고, 오른쪽부터 현재 요소까지의 최소값을 right_arr에 저장합니다.

이 과정에서 left_min과 right_min이 업데이트됩니다.

이후, 배열의 두 번째 요소부터 두 번째 마지막 요소까지 순회합니다.

현재 요소가 left_arr와 right_arr의 값보다 큰 경우, 끝까지 남을 수 없으므로 continue로 다음 요소로 넘어갑니다.

그렇지 않은 경우 answer를 증가시킵니다.

마지막으로, 계산된 answer를 반환합니다.

##### 결론

이 알고리즘은 배열을 두 번 순회하면서 각 요소에 대해 두 개의 비교 연산을 수행하므로 효율적입니다.
