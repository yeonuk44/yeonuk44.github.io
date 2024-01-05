---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sharing_A_Pizza_1
title: 피자 나눠 먹기 1 (with.Java)
# title: Sharing a Pizza 1 (with.Java)
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
date: 2024-01-05 09:00:00 +0900
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

## "개미 군단" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

개미 군단이 사냥을 나가려고 합니다.

개미군단은 사냥감의 체력에 딱 맞는 병력을 데리고 나가려고 합니다.

장군개미는 5의 공격력을, 병정개미는 3의 공격력을 일개미는 1의 공격력을 가지고 있습니다.

예를 들어 체력 23의 여치를 사냥하려고 할 때, 일개미 23마리를 데리고 가도 되지만, 장군개미 네 마리와 병정개미 한 마리를 데리고 간다면 더 적은 병력으로 사냥할 수 있습니다.

사냥감의 체력 hp가 매개변수로 주어질 때, 사냥감의 체력에 딱 맞게 최소한의 병력을 구성하려면 몇 마리의 개미가 필요한지를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

hp는 자연수입니다.

0 ≤ hp ≤ 1000

#### 입출력 예시

| hp  | result |
| --- | ------ |
| 23  | 5      |
| 24  | 6      |
| 999 | 201    |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int hp) {
        int answer = 0;
        int quo = 0;
        int rem = hp;
        for(int i = 5; i >= 1; i -= 2){
            quo = rem / i;
            rem = rem % i;
            if(quo != 0){
                answer += quo;
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

입력: hp - 회복해야 하는 체력.

출력: 힐링 아이템을 사용하여 회복된 횟수.

Greedy 알고리즘 활용: Greedy 알고리즘을 사용하여 최대한 큰 단위의 힐링 아이템을 사용하는 방식으로 구현되어 있습니다.

사용된 함수 소개:

rem / i와 rem % i: 나눗셈 연산을 통해 힐링 아이템을 사용한 횟수(quo)와 나머지 체력(rem)을 계산합니다.

개선 가능한 점:

상수 사용: 현재 코드에서 5와 2는 상수로 사용되어 있습니다. 이러한 상수를 변수로 대체하여 유연성을 높일 수 있습니다.

효율성: 코드는 주어진 힐링 아이템의 종류에 따라 순차적으로 확인하며 힐링을 시도하고 있습니다. 이를 통해 최적의 힐링 시나리오를 찾아내는 방법을 고려할 수 있습니다.

입력 예외 처리: 음수 또는 잘못된 값이 입력될 경우에 대한 예외 처리가 필요할 수 있습니다.

이러한 개선 사항을 고려하여 코드를 더욱 완전하게 만들 수 있습니다.
