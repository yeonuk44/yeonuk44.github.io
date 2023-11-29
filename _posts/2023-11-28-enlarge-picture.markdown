---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Enlarge_Picture
title: Enlarge Picture (with.Java)
# title: Enlarge Picture (with.Java)
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
date: 2023-11-28 09:00:00 +0900
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

## "날짜 비교하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 배열 date1과 date2가 주어집니다.

두 배열은 각각 날짜를 나타내며 [year, month, day] 꼴로 주어집니다. 각 배열에서 year는 연도를, month는 월을, day는 날짜를 나타냅니다.

만약 date1이 date2보다 앞서는 날짜라면 1을, 아니면 0을 return 하는 solution 함수를 완성해 주세요.

#### 입출력 예시

| date1          | date2          | result |
| -------------- | -------------- | ------ |
| [2021, 12, 28] | [2021, 12, 29] | 1      |
| [1024, 10, 24] | [1024, 10, 24] | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] date1, int[] date2) {
        int answer = 0;
        for(int i = 2; i >= 0; i--){
            if(date1[i] < date2[i]){
                answer = 1;
            }else if(date1[i] > date2[i]){
                answer = 0;
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

int answer = 0;: 결과를 저장할 정수형 변수 answer를 초기화합니다. 초기값은 0입니다.

for(int i = 2; i >= 0; i--) : 2부터 시작하여 0까지 반복하는 루프를 사용하여 각 날짜 필드 (년, 월, 일)를 비교합니다. 루프는 년부터 시작하고, 년, 월, 일 순서로 비교합니다.

if(date1[i] < date2[i]) : 현재 필드에서 date1 값이 date2 값보다 작은 경우:

answer를 1로 설정합니다. 이는 date1이 date2보다 이전인 경우를 나타냅니다
.
else if(date1[i] > date2[i]) : 현재 필드에서 date1 값이 date2 값보다 큰 경우:

answer를 0으로 설정합니다. 이는 date1이 date2보다 이후인 경우를 나타냅니다.

return answer;: 날짜를 비교한 결과를 나타내는 answer 값을 반환합니다.
