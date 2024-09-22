---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_the_three_dice
title: 백준 2480번, 주사위 세개 (with.Java)
# title: Baekjun 2480, 3 dice (with.Java)
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
date: 2024-09-22 09:00:00 +0900
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

## 백준 2480번, 주사위 세개 (with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

1에서부터 6까지의 눈을 가진 3개의 주사위를 던져서 다음과 같은 규칙에 따라 상금을 받는 게임이 있다.

같은 눈이 3개가 나오면 10,000원+(같은 눈)×1,000원의 상금을 받게 된다.

같은 눈이 2개만 나오는 경우에는 1,000원+(같은 눈)×100원의 상금을 받게 된다.

모두 다른 눈이 나오는 경우에는 (그 중 가장 큰 눈)×100원의 상금을 받게 된다.

예를 들어, 3개의 눈 3, 3, 6이 주어지면 상금은 1,000+3×100으로 계산되어 1,300원을 받게 된다.

또 3개의 눈이 2, 2, 2로 주어지면 10,000+2×1,000 으로 계산되어 12,000원을 받게 된다.

3개의 눈이 6, 2, 5로 주어지면 그중 가장 큰 값이 6이므로 6×100으로 계산되어 600원을 상금으로 받게 된다.

3개 주사위의 나온 눈이 주어질 때, 상금을 계산하는 프로그램을 작성 하시오.

#### 입력

첫째 줄에 3개의 눈이 빈칸을 사이에 두고 각각 주어진다.

#### 출력

첫째 줄에 게임의 상금을 출력 한다.

### 문제 풀이

```java
import java.util.Scanner;
class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int a = scan.nextInt();
        int b = scan.nextInt();
        int c = scan.nextInt();
        int answer = 0;

        if (a == b && b == c) {
            answer = 10000 + (a * 1000);
        }else if(a == b || a == c){
            answer = 1000 + (a * 100);
        }else if(b == c){
            answer = 1000 + (b * 100);
        }else{
            if(a >= b && a >= c){
                answer = a * 100;
            }else if(b >= a && b >= c){
                answer = b * 100;
            }else{
                answer = c * 100;
            }
        }
        System.out.print(answer);
    }
}
```

#### 풀이 설명

int answer = 0;를 선언하여 결과를 저장할 변수를 초기화합니다.

- 세 개의 주사위 값이 모두 같은 경우: if (a == b && b == c) 조건문을 통해 확인하고, 10000 + (a \_ 1000) 값을 answer에 저장합니다.
- 두 개의 주사위 값이 같은 경우: else if(a == b || a == c) 조건문을 통해 a가 두 개 이상 같을 때, 1000 + (a \_ 100) 값을 answer에 저장합니다. else if(b == c) 조건문을 통해 b와 c가 같을 때, 1000 + (b \* 100) 값을 answer에 저장합니다.
- 세 개의 주사위 값이 모두 다른 경우: else 블록에서 세 숫자 중 가장 큰 값을 찾습니다. a, b, c를 비교하여 가장 큰 값에 100을 곱한 값을 answer에 저장합니다.

이 코드는 주사위 게임의 결과를 계산하는 프로그램입니다.

세 개의 주사위 값을 입력받아 세 값이 같을 때, 두 값이 같을 때, 세 값이 모두 다를 때의 경우에 따라 점수를 계산하여 출력합니다.

감사합니다!
