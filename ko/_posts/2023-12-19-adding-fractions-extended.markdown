---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Adding_Fractions_Extended
title: 분수의 덧셈에 대하여 (확장편)
# title: About adding fractions (extended)
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
date: 2023-12-19 09:00:00 +0900
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

## "분수의 덧셈" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

첫 번째 분수의 분자와 분모를 뜻하는 numer1, denom1, 두 번째 분수의 분자와 분모를 뜻하는 numer2, denom2가 매개변수로 주어집니다.

두 분수를 더한 값을 기약 분수로 나타냈을 때 분자와 분모를 순서대로 담은 배열을 return 하도록 solution 함수를 완성해보세요.

#### 입출력 예시

| numer1 | denom1 | numer2 | denom2 | result  |
| ------ | ------ | ------ | ------ | ------- |
| 1      | 2      | 3      | 4      | [5, 4]  |
| 9      | 2      | 1      | 3      | [29, 6] |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int numer1, int denom1, int numer2, int denom2) {
        int newNumer = numer1 * denom2 + numer2 * denom1;
        int newDenom = denom1 * denom2;
        int gcd = findGCD(newNumer, newDenom);
        newNumer /= gcd;
        newDenom /= gcd;

        int[] result = {newNumer, newDenom};
        return result;
    }
    public int findGCD(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return Math.abs(a);
    }
}
```

#### 풀이 설명

int newNumer = numer1 _ denom2 + numer2 _ denom1;: 주어진 두 분수의 분자를 더하여 새로운 분자 newNumer를 계산합니다.

int newDenom = denom1 \* denom2;: 주어진 두 분수의 분모를 곱하여 새로운 분모 newDenom를 계산합니다.

int gcd = findGCD(newNumer, newDenom);: findGCD 함수를 호출하여 newNumer와 newDenom의 최대공약수 (gcd)를 찾습니다.

newNumer /= gcd;과 newDenom /= gcd;: newNumer와 newDenom을 최대공약수로 나누어 기약분수를 얻습니다.

int[] result = {newNumer, newDenom};: 기약분수인 newNumer와 newDenom을 배열에 담아 result 배열에 저장합니다.

return result;: 계산된 결과인 기약분수를 반환합니다.

findGCD 함수는 두 수의 최대공약수를 계산하기 위해 유클리드 호제법을 사용합니다. 이 코드는 두 분수를 더하고, 결과를 기약분수로 정규화하는 간단한 분수 연산을 수행합니다.
