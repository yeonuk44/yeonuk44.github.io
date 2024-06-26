---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Iced_Americano
title: 아이스 아메리카노(with.Java)
# title: Iced Americano (with.Java)

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
date: 2024-02-02 09:00:00 +0900
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

## "아이스 아메리카노" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 추운 날에도 아이스 아메리카노만 마십니다.

아이스 아메리카노는 한잔에 5,500원입니다.

머쓱이가 가지고 있는 돈 money가 매개변수로 주어질 때, 머쓱이가 최대로 마실 수 있는 아메리카노의 잔 수와 남는 돈을 순서대로 담은 배열을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

0 < money ≤ 1,000,000

#### 입출력 예시

| money  | result    |
| ------ | --------- |
| 5,500  | [1, 0]    |
| 15,000 | [2, 4000] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int money) {
        int[] answer = new int[2];
        answer[0] = money / 5500;
        answer[1] = money % 5500;
        return answer;
    }
}
```

### 풀이 설명

int[] answer = new int[2];: 두 개의 정수를 저장할 배열 answer를 생성합니다.

answer[0] = money / 5500;: 입력된 금액 money를 5500으로 나눈 몫을 배열의 첫 번째 요소에 저장합니다. 이는 5500으로 몇 번 나누어지는지를 나타냅니다.

answer[1] = money % 5500;: 입력된 금액 money를 5500으로 나눈 나머지를 배열의 두 번째 요소에 저장합니다. 이는 5500으로 나누었을 때 남는 금액을 나타냅니다.

return answer;: 계산된 몫과 나머지가 저장된 배열 answer를 반환합니다.

이 코드는 입력된 금액을 5500으로 나누어 몫과 나머지를 배열에 담아 반환합니다.
