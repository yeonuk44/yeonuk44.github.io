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

이번에 분수의 덧셈 문제를 해결하며 배웠던 것을 정리할 수 있는 시간을 가졌습니다.

지금부터 정리한 바를 공유드리고자 합니다.

분수의 덧셈을 Java로 해결한 코드를 보며 설명드리겠습니다.

{:data-align="center"}

<!-- outline-end -->

### Java로 해결한 코드

```java
class Solution {
    public int[] solution(int numer1, int denom1, int numer2, int denom2) {
        // 분자와 분모를 더합니다.
        int newNumer = numer1 * denom2 + numer2 * denom1;
        int newDenom = denom1 * denom2;

        // 최대 공약수를 구합니다.
        int gcd = findGCD(newNumer, newDenom);

        // 분자와 분모를 최대 공약수로 나누어 기약 분수를 얻습니다.
        newNumer /= gcd;
        newDenom /= gcd;

        int[] result = {newNumer, newDenom};
        return result;
    }

    // 최대 공약수를 계산하는 함수
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

### 분수의 덧셈을 하는 방법

주어진 두 분수 a/b와 c/d를 더하기 위해서는 다음과 같이 분자와 분모를 더합니다.

```java
newNumer = a * d + c * b;
newDenom = b * d;
```

여기서 newNumer는 새로운 분자를 나타내고, newDenom은 새로운 분모를 나타냅니다.

#### 최대 공약수(GCD) 구하기

최대 공약수는 분수를 기약 분수로 만들기 위해 사용됩니다.

주어진 newNumer와 newDenom을 가지고 최대 공약수(GCD)를 계산합니다.

##### 최대 공약수를 구하는 다양한 방법

1. 유클리드 호제법 (Euclidean Algorithm): 이 방법은 두 수의 최대공약수를 구하는 가장 효율적인 방법 중 하나입니다. 유클리드 호제법은 두 수를 나눈 나머지를 이용하여 최대공약수를 찾는 방법입니다.
   예를 들어, 두 수 a와 b의 최대공약수를 GCD(a, b)라고 하면 다음과 같이 계산합니다.

```java
GCD(a, b) = GCD(b, a % b)
```

2. 소인수분해를 이용한 방법: 이 방법은 두 수를 소인수분해하여 공통된 소인수를 찾는 방법입니다. 예를 들어, 18과 24의 최대공약수를 구하려면 먼저 각 수를 소인수분해합니다.
   18 = 2 _ 3^2
   24 = 2^3 _ 3
   그런 다음, 각 소인수의 지수 부분에서 작은 값들을 선택하여 공통된 소인수를 찾습니다. 위의 예에서는 2^1과 3^1이 공통된 소인수이므로 최대공약수는 2^1 \* 3^1 = 6 입니다.
3. 최대공약수를 찾는 알고리즘 사용: 프로그래밍 언어나 수학 라이브러리에서는 최대공약수를 구하는 함수나 메서드를 제공합니다. 이러한 함수를 사용하면 간단하게 최대공약수를 찾을 수 있습니다.

저는 위의 방법들 중 1번의 유클리드 호제법을 사용하여 문제를 풀었습니다.

```java
public int findGCD(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return Math.abs(a);
}
```

최대 공약수는 기약 분수를 구하기 위해 사용한다고 말씀드렸습니다.

기약 분수에 대해서도 간단하게 알아보겠습니다.

##### 기약 분수

기약 분수(또는 약분 분수)는 분자와 분모의 최대공약수(GCD)가 1인 분수를 의미합니다. 즉, 분수를 더 이상 약분할 수 없는 형태로 간소화한 분수를 말합니다. 예를 들어, 2/4는 1/2로 기약 분수로 간소화할 수 있습니다.

기약 분수로 나타내면 분수를 간단하게 표현할 수 있고, 연산 및 비교가 더 쉬워집니다. 따라서, 분수를 다룰 때 기약 분수로 변환하는 것은 일반적으로 바람직합니다.

기약 분수로 변환하는 과정은 주어진 분자와 분모의 최대공약수(GCD)를 계산하고, 이 최대공약수로 분자와 분모를 나누는 것입니다. 이렇게 하면 분수가 가장 단순한 형태로 표현됩니다.

최대 공약수를 구했다면 다음 단계로 넘어갑니다.

##### 마무리

분자와 분모를 최대 공약수로 나눕니다. 구한 최대 공약수를 사용하여 newNumer와 newDenom을 나누어 기약 분수를 얻습니다.

```java
newNumer /= gcd;
newDenom /= gcd;
```

위와 같은 공식을 따라서 분수 합의 공식과 최대 공약수를 사용하여 분수를 기약 분수로 나타내어 보았습니다.
