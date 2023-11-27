---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_An_Integer
title: 정수 찾기(with.Java)
# title: Find an integer (with.Java)
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
date: 2023-11-26 09:00:00 +0900
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

## "정수 찾기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 리스트 num_list와 찾으려는 정수 n이 주어질 때, num_list안에 n이 있으면 1을 없으면 0을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예시

| num_list            | n   | result |
| ------------------- | --- | ------ |
| [1, 2, 3, 4, 5]     | 3   | 1      |
| [15, 98, 23, 2, 15] | 20  | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] num_list, int n) {
        int answer = 0;
        for(int temp: num_list){
            if(temp == n){
                answer = 1;
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

int answer = 0;: 결과를 저장할 정수형 변수 answer를 초기화합니다. 초기값은 0입니다.

for(int temp : num_list) : 정수 배열 num_list를 반복하면서 각 요소 temp를 검사합니다.

if(temp == n) : 현재 요소 temp가 입력으로 받은 n과 같은 경우:

answer를 1로 설정합니다.

return answer;: 판단 결과를 나타내는 answer 값을 반환합니다.
