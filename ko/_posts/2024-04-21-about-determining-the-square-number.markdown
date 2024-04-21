---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Determining_The_Square_Number
title: 제곱수 판별하기 (with.Java)
# title: Determining the square number (with.Java)
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
date: 2024-04-21 09:00:00 +0900
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

## "제곱수 판별하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

어떤 자연수를 제곱했을 때 나오는 정수를 제곱수라고 합니다.

정수 n이 매개변수로 주어질 때, n이 제곱수라면 1을 아니라면 2를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ n ≤ 1,000,000

#### 입출력 예시

| n   | result |
| --- | ------ |
| 144 | 1      |
| 976 | 2      |

<!-- | str1                     | str2   | result |
| ------------------------ | ------ | ------ |
| "ab6CDE443fgh22iJKlmn1o" | "6CD"  | 1      |
| "ppprrrogrammers"        | "pppp" | 2      |
| "AbcAbcA"                | "AAA"  | 2      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        for(int i = 1; i <= 1000; i++){
            if(i * i == n){
                answer = 1;
                break;
            }else if(i * i > n){
                answer = 2;
                break;
            }
        }
        return answer;
    }
}
```

### 풀이 설명

int answer = 0;: 결과값을 저장할 변수 answer를 0으로 초기화합니다.

for(int i = 1; i <= 1000; i++): 1부터 1000까지의 수를 순차적으로 확인하기 위한 반복문입니다.

if(i \* i == n): 현재 수 i를 제곱한 값이 n과 같다면, n은 제곱수입니다. 따라서 answer를 1로 설정하고 반복문을 종료합니다.

else if(i \* i > n): 현재 수 i를 제곱한 값이 n보다 크다면, n은 제곱수가 아닙니다. 따라서 answer를 2로 설정하고 반복문을 종료합니다.

return answer;: 최종적인 결과값 answer를 반환합니다.

이 코드는 1부터 1000까지의 수를 차례대로 제곱하여 n과 비교하면서 n이 제곱수인지 아닌지를 판별합니다. 반환되는 값은 다음과 같습니다:

0: n이 1부터 1000까지의 수들의 제곱으로 표현되지 않는 경우
1: n이 1부터 1000까지의 수들 중 하나의 제곱으로 표현되는 경우
2: n이 1부터 1000까지의 수들의 제곱보다 큰 경우
