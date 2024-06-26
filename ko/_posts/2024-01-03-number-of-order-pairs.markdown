---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Of_Order_Pairs
title: 순서쌍의 개수(with.Java)
# title: Number of order pairs (with.Java)
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
date: 2024-01-03 09:00:00 +0900
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

## "순서쌍의 개수" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

순서쌍이란 두 개의 숫자를 순서를 정하여 짝지어 나타낸 쌍으로 (a, b)로 표기합니다.

자연수 n이 매개변수로 주어질 때 두 숫자의 곱이 n인 자연수 순서쌍의 개수를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

1 ≤ n ≤ 1,000,000

#### 입출력 예시

| n   | result |
| --- | ------ |
| 20  | 6      |
| 100 | 9      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        for(int i = 1; i <= n; i++){
            if(n % i == 0){
                answer++;
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

입력: n - 약수의 개수를 계산할 정수.

출력: n의 약수의 개수.

사용된 함수 소개:
n % i == 0: 나머지 연산을 통해 i가 n의 약수인지를 확인합니다. 만약 나머지가 0이면 i는 n의 약수입니다.

개선 가능한 점:
성능 개선: 현재 코드는 모든 수에 대해 약수를 확인하므로 성능에 영향을 줄 수 있습니다. 성능을 개선하기 위해 약수는 주어진 수의 제곱근까지만 확인하여도 충분합니다.

코드 모듈화: 함수 내의 기능을 작은 모듈로 나누어 코드의 가독성과 재사용성을 높일 수 있습니다.

수학적 최적화: 약수의 개수는 수학적으로도 풀 수 있는 문제이므로, 더 효율적이고 간결한 알고리즘을 고려할 수 있습니다.
