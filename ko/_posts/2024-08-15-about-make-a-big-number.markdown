---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Make_A_Big_Number
title: 큰 수 만들기(with.Java)
# title: Make a big number (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding tes, greedy]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-15 09:00:00 +0900
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

## 큰 수 만들기(with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

어떤 숫자에서 k개의 수를 제거했을 때 얻을 수 있는 가장 큰 숫자를 구하려 합니다.

예를 들어, 숫자 1924에서 수 두 개를 제거하면 [19, 12, 14, 92, 94, 24] 를 만들 수 있습니다.

이 중 가장 큰 숫자는 94 입니다.

문자열 형식으로 숫자 number와 제거할 수의 개수 k가 solution 함수의 매개변수로 주어집니다.

number에서 k 개의 수를 제거했을 때 만들 수 있는 수 중 가장 큰 숫자를 문자열 형태로 return 하도록 solution 함수를 완성하세요.

#### 제한사항

- number는 2자리 이상, 1,000,000자리 이하인 숫자입니다.
- k는 1 이상 number의 자릿수 미만인 자연수입니다.

#### 입출력 예시

| number       | k   | return   |
| ------------ | --- | -------- |
| "1924"       | 2   | "94"     |
| "1231234"    | 3   | "3234"   |
| "4177252841" | 4   | "775841" |

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String number, int k) {
        String answer = "";
        StringBuilder sb = new StringBuilder();
        int idx = 0;
        int num;
        for(int i = 0; i < number.length() - k; i++){
            num = 0;
            for(int j = idx; j <= k + i; j++){
                if(num < number.charAt(j) - '0'){
                    num = number.charAt(j) - '0';
                    idx = j + 1;
                }
            }
            sb.append(num);
        }
        return sb.toString();
    }
}
```

### 풀이 설명

- StringBuilder sb를 사용하여 결과를 저장합니다.
- idx 변수는 현재까지 선택한 숫자의 인덱스를 나타냅니다.
- num 변수는 선택한 숫자 중 가장 큰 숫자를 저장합니다.
- 바깥쪽 반복문은 결과 문자열의 길이가 number.length() - k가 될 때까지 반복합니다.
- 안쪽 반복문은 현재까지 선택한 숫자를 제외한 나머지 숫자 중 가장 큰 숫자를 선택합니다.
- 선택한 가장 큰 숫자를 결과에 추가합니다.

### 결론

이 코드는 Greedy 방법을 사용하여 문제를 해결합니다.

Greedy 방법은 각 단계에서 지금 당장 최선의 선택을 하며 결과적으로 최적해를 찾는 알고리즘입니다.
