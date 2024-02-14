---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Removing_Vowels
title: 모음 제거(with. Java)
# title: Removing vowels (with. Java)
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
date: 2024-02-14 09:00:00 +0900
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

## "팩토리얼" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

i팩토리얼 (i!)은 1부터 i까지 정수의 곱을 의미합니다. 예를들어 5! = 5 _ 4 _ 3 _ 2 _ 1 = 120 입니다. 정수 n이 주어질 때 다음 조건을 만족하는 가장 큰 정수 i를 return 하도록 solution 함수를 완성해주세요.

- i! ≤ n

#### 제한사항

- 0 < n ≤ 3,628,800

#### 입출력 예시

| n       | result |
| ------- | ------ |
| 3628800 | 10     |
| 7       | 3      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        int temp = 1;
        for(int i = 2; i <= 10; i++){
            for(int j = i; j >= 2; j--){
                temp *= j;
            }
            if(temp == n){
                answer = i;
                return answer;
            } else if(temp > n){
                answer = i - 1;
                return answer;
            } else {
                temp = 1;
            }
        }
        return answer;
    }
}
```

### 풀이 설명

solution(int n): 주어진 정수 n을 팩토리얼로 표현할 수 있는 최소한의 숫자 개수를 반환합니다.

for 문을 이용하여 2부터 10까지의 숫자에 대해 팩토리얼을 계산합니다.

내부 for 문을 통해 현재 숫자부터 2까지의 팩토리얼을 계산하고, 이를 temp에 저장합니다.

계산한 팩토리얼이 n과 일치하면 해당 숫자를 결과로 반환합니다.

팩토리얼이 n보다 크면 직전 숫자가 최소 개수이므로 결과로 반환합니다.

**코드 장점**

- 간단한 구현: 문제를 해결하는 데 필요한 구현이 간단하다.
- 직관적인 로직: 주어진 조건을 순차적으로 검사하여 직관적인 로직을 갖추고 있다.

**코드 단점**

- 특정 범위에만 적용 가능: 현재는 2부터 10까지의 숫자에 대해서만 팩토리얼을 계산하고 있어, 이 범위를 벗어나면 정확한 결과를 얻을 수 없다.
