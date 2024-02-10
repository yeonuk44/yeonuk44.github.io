---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Of_Dice
title: Number of dice (with.Java)
# title: Number of dice (with.Java)
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
date: 2024-02-10 09:00:00 +0900
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

## "배열 회전시키기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수가 담긴 배열 numbers와 문자열 direction가 매개변수로 주어집니다.

배열 numbers의 원소를 direction방향으로 한 칸씩 회전시킨 배열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 3 ≤ numbers의 길이 ≤ 20
- direction은 "left" 와 "right" 둘 중 하나입니다.

#### 입출력 예시

| numbers                   | direction | result                    |
| ------------------------- | --------- | ------------------------- |
| [1, 2, 3]                 | "right"   | [3, 1, 2]                 |
| [4, 455, 6, 4, -1, 45, 6] | "left"    | [455, 6, 4, -1, 45, 6, 4] |

|

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] numbers, String direction) {
        int[] answer = new int[numbers.length];
        if(direction.equals("right")){
            for(int i = 0; i < numbers.length; i++){
                if(answer.length == i + 1){
                    answer[0] = numbers[i];
                }else{
                    answer[i + 1] = numbers[i];
                }
            }
        }else{
            for(int i = 0; i < numbers.length; i++){
                if(answer.length == i + 1){
                    answer[i] = numbers[0];
                }else{
                    answer[i] = numbers[i + 1];
                }
            }
        }
        return answer;
    }
}
```

### 풀이 설명

주어진 방향이 "right"일 경우: 배열의 각 요소를 한 칸씩 오른쪽으로 이동시킵니다.

마지막 요소는 첫 번째 요소로 이동합니다.

주어진 방향이 "left"일 경우: 배열의 각 요소를 한 칸씩 왼쪽으로 이동시킵니다.

첫 번째 요소는 마지막 요소로 이동합니다.

위의 두 동작을 수행하면 배열을 회전시킬 수 있습니다.

**사용된 함수 설명**
equals(): 문자열을 비교하는 메서드입니다.

문자열을 비교할 때 == 연산자를 사용하지 않는 이유는 문자열은 참조 타입이기 때문입니다.

equals() 메서드를 사용하면 두 문자열의 실제 내용을 비교할 수 있습니다.

**코드 분석**
equals() 메서드를 사용하여 문자열을 비교하고 있습니다.

direction.equals("right")와 direction.equals("left")는 주어진 방향이 "right" 또는 "left"인지 확인하는 조건문입니다.

for 루프를 통해 배열을 회전시키고 있습니다.

오른쪽으로 이동할 때는 마지막 요소를 첫 번째로, 왼쪽으로 이동할 때는 첫 번째 요소를 마지막으로 이동시킵니다.

**코드 장점**
equals() 메서드 사용: 문자열을 비교할 때 equals() 메서드를 사용함으로써 실제 문자열의 내용을 비교하고 있습니다.

이는 문자열이 참조 타입이기 때문에 내용을 비교하기 위해서는 equals()를 사용하는 것이 올바릅니다.
