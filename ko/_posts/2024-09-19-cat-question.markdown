---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Cat_Question
title: 백준 10171번, 고양이 (with.Java)
# title: Baekjun 10171, Cat (with.Java)
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
date: 2024-09-19 09:00:00 +0900
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

## 백준 10171번 고양이 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

두 정수 A와 B를 입력받은 다음, A/B를 출력하는 프로그램을 작성하시오.

#### 입력

첫째 줄에 A와 B가 주어진다. (0 < A, B < 10)

#### 출력

첫째 줄에 A/B를 출력한다.

실제 정답과 출력값의 절대오차 또는 상대오차가 10-9 이하이면 정답이다.

### 문제 풀이

```java
import java.util.Scanner;

class Main{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        double a = scan.nextDouble();
        double b = scan.nextDouble();
        scan.close();
        System.out.print(String.format("%.10f", a / b));
    }
}

```

#### 풀이 설명

문제를 풀며 float와 double의 차이를 생각해볼 수 있었습니다.

Java에서는 double과 float 두 가지 기본 데이터 타입을 사용하여 부동 소수점 숫자를 표현합니다.

이 두 타입은 저장할 수 있는 값의 범위와 정밀도에서 차이가 있으며, 각기 다른 장단점이 있습니다.

##### 차이점

###### 정밀도와 저장 범위:

float:

- 32비트 (4바이트) 크기
- 약 7자리의 유효 숫자를 가짐
- 표현할 수 있는 값의 범위는 약 ±1.4E-45에서 ±3.4E+38

double:

- 64비트 (8바이트) 크기
- 약 15자리의 유효 숫자를 가짐
- 표현할 수 있는 값의 범위는 약 ±4.9E-324에서 ±1.8E+308

###### 정밀도 및 계산:

double은 float보다 두 배의 비트 수를 가지므로 더 많은 유효 숫자를 표현할 수 있어 정밀도가 높습니다.

이는 과학적 계산, 금융 계산 등 높은 정밀도가 요구되는 경우에 유리합니다.

float는 더 적은 메모리를 사용하며, 정밀도가 상대적으로 낮지만 일부 그래픽 응용 프로그램이나 메모리 사용이 중요한 경우에 유리할 수 있습니다.

##### 장단점

float:

- 장점 : 메모리 사용량이 적어 대규모 배열이나 메모리 제약이 있는 환경에서 유리합니다. 일부 그래픽 프로그래밍에서 더 나은 성능을 제공할 수 있습니다.
- 단점 : 정밀도가 낮아 많은 유효 숫자를 다루는 경우 부정확할 수 있습니다. 계산 시 오차가 더 많이 발생할 수 있습니다.

double:

- 장점:정밀도가 높아 많은 유효 숫자를 정확하게 다룰 수 있습니다. 기본 부동 소수점 타입이므로 명시적으로 타입을 지정하지 않아도 됩니다.
- 단점:메모리 사용량이 float보다 두 배 많습니다.
  일부 성능 민감한 응용 프로그램에서는 더 느릴 수 있습니다.

### 결론

예를 들어, 그래픽 응용 프로그램에서는 float을 사용하여 성능을 최적화할 수 있지만, 금융 계산에서는 double을 사용하여 높은 정밀도를 유지하는 것이 중요합니다.

메모리 제약이 크지 않고 정밀도가 중요한 경우: double 사용

메모리 사용을 최소화해야 하고, 정밀도가 상대적으로 덜 중요한 경우: float 사용

감사합니다!
