---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Addition_Of_Hidden_Numbers_1
title: Addition of hidden numbers 1 (with.Java)
# post specific
# title: Addition of hidden numbers 1 (with.Java)
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
date: 2024-02-16 09:00:00 +0900
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

## "소인수분해" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

소인수분해란 어떤 수를 소수들의 곱으로 표현하는 것입니다.

예를 들어 12를 소인수 분해하면 2 _ 2 _ 3 으로 나타낼 수 있습니다.

따라서 12의 소인수는 2와 3입니다.

자연수 n이 매개변수로 주어질 때 n의 소인수를 오름차순으로 담은 배열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 2 ≤ n ≤ 10,000

#### 입출력 예시

| n   | result       |
| --- | ------------ |
| 12  | [2, 3]       |
| 17  | [ 17 ]       |
| 420 | [2, 3, 5, 7] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int[] solution(int n) {
        List<Integer> factors = new ArrayList<>();

        for (int i = 2; i <= n; i++) {
            while (n % i == 0) {
                factors.add(i);
                n /= i;
            }
        }

        Set<Integer> set = new HashSet<>();

        List<Integer> result = new ArrayList<>();

        for (int element : factors) {
            if (set.add(element)) {
                result.add(element);
            }
        }

        int[] answer = new int[result.size()];
        for (int i = 0; i < result.size(); i++) {
            answer[i] = result.get(i);
        }

        return answer;
    }
}
```

### 풀이 설명

- List<Integer> factors: 소인수를 저장하는 리스트. 주어진 수 n을 2부터 시작하여 나눌 수 있는 소인수를 찾아 리스트에 추가한다.
- Set<Integer> set: 중복된 소인수를 제외하기 위한 HashSet. 중복을 방지하기 위해 사용한다.
- List<Integer> result: 중복된 소인수를 제외하고 저장할 리스트.
- 소인수 분해: for문을 통해 주어진 수 n을 2부터 시작하여 나눌 수 있는 소인수를 찾고, 해당 소인수를 factors 리스트에 추가하고 n을 갱신한다.
- 중복된 소인수 제외: set을 사용하여 중복된 소인수를 제외하면서 고유한 소인수들을 result 리스트에 추가한다.
- 배열로 변환: result 리스트를 배열로 변환하여 최종 결과인 answer로 반환한다.

**코드 장점**

- HashSet 사용: 중복된 소인수를 제외하기 위해 HashSet을 사용하여 중복을 간단히 제거할 수 있다.
- List 활용: 소인수를 찾고, 중복된 소인수를 제외한 결과를 저장하는 데에 List를 효과적으로 활용했다.

**코드 단점**

- 리스트 변환: List를 int[] 배열로 변환하는 과정이 복잡해 보일 수 있지만, Java 8부터는 람다식 및 스트림 API를 사용하여 더 간단하게 표현할 수 있습니다.
