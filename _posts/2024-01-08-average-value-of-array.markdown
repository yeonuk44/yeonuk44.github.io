---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Average_Value_Of_Array
title: Average value of an array (with.Java)
# title: Average value of an array (with.Java)
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
date: 2024-01-08 09:00:00 +0900
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

## "피자 나눠 먹기 3" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이네 피자가게는 피자를 두 조각에서 열 조각까지 원하는 조각 수로 잘라줍니다.

피자 조각 수 slice와 피자를 먹는 사람의 수 n이 매개변수로 주어질 때, n명의 사람이 최소 한 조각 이상 피자를 먹으려면 최소 몇 판의 피자를 시켜야 하는지를 return 하도록 solution 함수를 완성해보세요.

#### 입출력 예시

| slice | n   | result |
| ----- | --- | ------ |
| 7     | 10  | 2      |
| 4     | 12  | 3      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int slice, int n) {
        int answer = 0;
        for(int i = 0; i < slice * n; i++){
            if(slice * i >= n){
                answer = i;
                break;
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

int answer = 0;: 결과 값을 저장할 변수 answer를 초기화합니다.

for (int i = 0; i < slice _ n; i++) : i를 0부터 slice _ n까지 반복합니다.

if (slice \* i >= n) : 현재 i에 slice를 곱한 값이 n보다 크거나 같은지 확인합니다.

answer = i;: 만약 조건을 만족하는 경우, answer에 현재의 i 값을 저장하고 반복문을 종료합니다.

break;: 조건을 만족하는 경우, 반복문을 종료합니다.

return answer;: 계산된 결과인 answer를 반환합니다.

이 코드는 slice를 n으로 나누는 몫을 계산하는데, n보다 크거나 같은 첫 번째 slice의 배수를 찾아서 반환합니다.
