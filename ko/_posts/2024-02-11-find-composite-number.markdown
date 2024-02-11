---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_Composite_Number
title: 합성수 찾기(with.Java)
# title: Find composite number (with.Java)
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
date: 2024-02-11 09:00:00 +0900
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

## "합성수 찾기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

약수의 개수가 세 개 이상인 수를 합성수라고 합니다.

자연수 n이 매개변수로 주어질 때 n이하의 합성수의 개수를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ n ≤ 100

#### 입출력 예시

| n   | result |
| --- | ------ |
| 10  | 5      |
| 15  | 8      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        int count = 0;
        for(int i = 1; i <= n; i++){
            for(int j = 1; j <= i; j++){
                if(i % j == 0){
                    count++;
                }
            }
            if(count > 2){
                answer++;
            }
            count = 0;
        }
        return answer;
    }
}
```

### 풀이 설명

solution(int n): 주어진 범위 내에서 각 숫자가 소수인지를 판별하고, 소수인 경우 answer를 증가시킵니다.

count: 각 숫자의 약수의 개수를 세는 변수로, 소수는 약수의 개수가 2여야 합니다.

for 문을 이용하여 1부터 n까지의 숫자를 반복하고, 내부에 중첩된 for 문을 이용하여 각 숫자의 약수를 찾습니다.

내부의 for 문에서 if(i % j == 0)는 j가 i의 약수인지를 확인하는 조건입니다.

약수의 개수가 2를 초과하면 해당 숫자는 소수가 아닙니다.

문제 해결: 주어진 범위 내에서 소수의 개수를 찾는 간단한 방법으로 문제를 해결합니다.

직관적: 코드가 직관적이며 이해하기 쉽게 작성되어 있습니다.

해당 코드는 간단하지만, 효율적인 소수 판별 알고리즘을 사용하지 않아서 큰 입력값에 대해서는 성능이 좋지 않을 수 있습니다.

이를 개선하기 위해서는 효율적인 소수 판별 알고리즘을 사용하는 것이 좋습니다.
