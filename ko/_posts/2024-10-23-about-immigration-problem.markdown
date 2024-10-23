---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Immigration_Problem
title: 입국심사 (with.Java)
# title: Immigration Problem(with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, binary search]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-23 09:00:00 +0900
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

## 입국심사 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

n명이 입국심사를 위해 줄을 서서 기다리고 있습니다.

각 입국심사대에 있는 심사관마다 심사하는데 걸리는 시간은 다릅니다.

처음에 모든 심사대는 비어있습니다.

한 심사대에서는 동시에 한 명만 심사를 할 수 있습니다.

가장 앞에 서 있는 사람은 비어 있는 심사대로 가서 심사를 받을 수 있습니다.

하지만 더 빨리 끝나는 심사대가 있으면 기다렸다가 그곳으로 가서 심사를 받을 수도 있습니다.

모든 사람이 심사를 받는데 걸리는 시간을 최소로 하고 싶습니다.

입국심사를 기다리는 사람 수 n, 각 심사관이 한 명을 심사하는데 걸리는 시간이 담긴 배열 times가 매개변수로 주어질 때, 모든 사람이 심사를 받는데 걸리는 시간의 최솟값을 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- 입국심사를 기다리는 사람은 1명 이상 1,000,000,000명 이하입니다.
- 각 심사관이 한 명을 심사하는데 걸리는 시간은 1분 이상 1,000,000,000분 이하입니다.
- 심사관은 1명 이상 100,000명 이하입니다.

#### 입출력 예

| n   | times  | return |
| --- | ------ | ------ |
| 6   | [7,10] | 28     |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### 문제 풀이

```java
import java.util.Arrays;

class Solution {
    public long solution(int n, int[] times) {
        long answer = 0;
        Arrays.sort(times);
        long left = 0;
        long right = times[times.length - 1] * (long)n;

        while(left <= right){
            long mid = (left + right) / 2;
            long test_num = 0;
            for(int i = 0; i < times.length; i++){
                test_num += mid / times[i];
            }
            if(test_num < n){
                left = mid + 1;
            }else{
                answer = mid;
                right = mid - 1;
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

주어진 심사관들이 주어진 시간 내에 n명의 사람을 심사할 수 있는 최소 시간을 구하는 문제를 해결합니다.

이를 위해 이진 탐색 알고리즘을 사용합니다.

먼저, 주어진 심사 시간 배열인 times를 오름차순으로 정렬합니다.

이는 최소 시간과 최대 시간을 설정하기 위해 필요한 단계입니다.

이후 left 변수는 0으로, right 변수는 가장 오래 걸리는 심사관의 시간(times 배열의 마지막 요소)과 n을 곱한 값으로 설정합니다.

이는 심사 시간이 최대로 걸릴 경우를 가정한 것입니다.

이진 탐색을 수행하면서, mid 값을 left와 right의 중간값으로 설정합니다.

mid는 현재의 평균 시간으로 간주되며, 각 심사관이 이 시간 내에 몇 명을 심사할 수 있는지를 계산합니다.

이를 위해 test_num 변수를 사용하여, 모든 심사관들이 mid 시간 동안 심사할 수 있는 총 인원 수를 구합니다.

test_num 값은 mid를 각 심사관의 심사 시간으로 나눈 값을 모두 더하여 계산합니다.

이후, test_num이 n보다 작다면, 이는 현재 시간(mid) 내에 모든 사람을 심사할 수 없음을 의미하므로, left를 mid + 1로 설정하여 더 많은 시간을 할당합니다.

반대로, test_num이 n 이상이라면, 이는 현재 시간(mid) 내에 모든 사람을 심사할 수 있음을 의미하므로, answer를 mid로 설정하고, right를 mid - 1로 설정하여 더 적은 시간을 할당해도 가능한지 확인합니다.

이 과정을 left가 right보다 커질 때까지 반복합니다.

최종적으로 answer에는 모든 사람을 심사할 수 있는 최소 시간이 저장됩니다.

이 알고리즘은 이진 탐색을 사용하여 시간 복잡도를 줄이고, 효율적으로 문제를 해결합니다.
