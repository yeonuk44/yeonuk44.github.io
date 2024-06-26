---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Ways_Divide_Beads
title: 구슬을 나누는 경우의 수(with.Java)
# title: Number of ways to divide beads (with.Java)
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
date: 2024-02-04 09:00:00 +0900
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

## "구슬을 나누는 경우의 수" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 구슬을 친구들에게 나누어주려고 합니다.

구슬은 모두 다르게 생겼습니다.

머쓱이가 갖고 있는 구슬의 개수 balls와 친구들에게 나누어 줄 구슬 개수 share이 매개변수로 주어질 때, balls개의 구슬 중 share개의 구슬을 고르는 가능한 모든 경우의 수를 return 하는 solution 함수를 완성해주세요.

#### 제한사항

1 ≤ balls ≤ 30

1 ≤ share ≤ 30

구슬을 고르는 순서는 고려하지 않습니다.

share ≤ balls

#### 입출력 예시

| balls | share | result |
| ----- | ----- | ------ |
| 3     | 2     | 3      |
| 5     | 3     | 10     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int balls, int share) {
        double answer = 1;

        for(int i = 0; i < share; i++){
            answer = answer * (balls - i) / (i+1);
        }

        return (int)answer;
    }
}
```

### 풀이 설명

이항 계수를 구하기 위해 팩토리얼 계산을 사용하여 효율적으로 경우의 수를 계산하고 있습니다.

결과를 double에서 int로 형변환하여 반환하고 있습니다. 숫자가 매우 커질 경우, answer에 1을 초기화하고 이를 계속해서 누적하면서 정수의 범위를 초과할 수 있습니다.

double로 형변환하고 나중에 다시 int로 변환하는 것은 부정확할 수 있습니다.

큰 숫자에 대한 계산은 정수 오버플로우의 가능성이 있습니다.

따라서 더 큰 숫자에 대한 계산을 위해 long 또는 BigInteger를 고려할 수 있습니다.

#### 개선 가능한 점

형변환 주의: 정수 계산의 정확성을 위해 answer를 계산할 때 double로 유지하고 필요한 경우 형변환을 고려합니다.

수학적 최적화: 경우의 수를 계산하는 부분에서 수학적 최적화를 고려하여 효율성을 높일 수 있습니다.

정수 오버플로우 방지: 큰 숫자에 대한 경우의 수를 계산할 때 오버플로우를 방지하기 위해 long 또는 BigInteger를 사용합니다.
