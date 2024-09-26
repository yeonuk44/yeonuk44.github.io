---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Target_Number_Problem
title: Target number (with.Java)
# title: Target number (with.Java)
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
date: 2024-09-26 09:00:00 +0900
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

## 타겟 넘버 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

초 단위로 기록된 주식가격이 담긴 배열 prices가 매개변수로 주어질 때, 가격이 떨어지지 않은 기간은 몇 초인지를 return 하도록 solution 함수를 완성하세요.

#### 제한사항

- prices의 각 가격은 1 이상 10,000 이하인 자연수입니다.
- prices의 길이는 2 이상 100,000 이하입니다.

#### 입출력 예

| prices          | return          |
| --------------- | --------------- |
| [1, 2, 3, 2, 3] | [4, 3, 1, 1, 0] |

<!-- | priorities         | location | return |
| ------------------ | -------- | ------ |
| [2, 1, 3, 2]       | 2        | 1      |
| [1, 1, 9, 1, 1, 1] | 0        | 5      | -->

### 문제 풀이

```java
class Solution {
    public int[] solution(int[] prices) {
        int[] answer = new int[prices.length];
        for(int i = 0; i < prices.length - 1; i++){
            int init_0 = prices[i];
            int sec = 0;

            for(int j = i + 1; j < prices.length; j++){
                int init_1 = prices[j];
                sec++;

                if(init_0 > init_1){
                    break;
                }
            }

            answer[i] = sec;
        }
        return answer;
    }
}
```

#### 풀이 설명

이 코드는 주식 가격의 배열을 입력받아 각 주식 가격이 몇 초 동안 떨어지지 않았는지를 계산하여 반환하는 문제를 해결합니다.

먼저 주식 가격이 떨어지지 않은 시간을 저장할 배열을 생성합니다.

이 배열의 길이는 입력 배열과 동일합니다.

첫 번째 반복문을 통해 각 주식 가격을 확인합니다.

마지막 주식 가격은 비교할 필요가 없으므로 주식 배열의 길이에서 하나를 뺀 만큼 반복합니다.

현재 주식 가격을 변수에 저장하고 주식 가격이 떨어지지 않은 시간을 저장할 변수를 초기화합니다.

두 번째 반복문을 통해 현재 주식 가격 이후의 주식 가격들을 확인합니다.

비교할 주식 가격을 변수에 저장하고 주식 가격이 떨어지지 않았으므로 시간을 1초 증가시킵니다.

현재 주식 가격이 비교할 주식 가격보다 크다면 주식 가격이 떨어진 것이므로 반복문을 종료합니다.

현재 주식 가격이 떨어지지 않은 시간을 배열에 저장합니다.

이 과정을 통해 모든 주식 가격에 대해 떨어지지 않은 시간을 계산한 후, 결과 배열을 반환합니다.

예를 들어 주식 가격 배열이 1, 2, 3, 2, 3인 경우 첫 번째 가격 1은 떨어지지 않은 시간이 4초, 두 번째 가격 2는 3초, 세 번째 가격 3은 1초, 네 번째 가격 2는 1초, 마지막 가격 3은 비교할 필요가 없으므로 0초입니다.

따라서 결과 배열은 4, 3, 1, 1, 0이 됩니다.

이 코드는 주식 가격이 떨어지지 않은 시간을 효율적으로 계산하여 배열 형태로 반환하는 문제를 해결합니다.
