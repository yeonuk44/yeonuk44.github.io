---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Oven_Clock
title: 백준 2525번, 오븐 시계 (with.Java)
# title: Baekjun no. 2525, oven clock (with.Java)
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
date: 2024-09-20 09:00:00 +0900
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

## 백준 2525번 오븐 시계 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

KOI 전자에서는 건강에 좋고 맛있는 훈제오리구이 요리를 간편하게 만드는 인공지능 오븐을 개발하려고 한다.

인공지능 오븐을 사용하는 방법은 적당한 양의 오리 훈제 재료를 인공지능 오븐에 넣으면 된다.

그러면 인공지능 오븐은 오븐구이가 끝나는 시간을 분 단위로 자동적으로 계산한다.

또한, KOI 전자의 인공지능 오븐 앞면에는 사용자에게 훈제오리구이 요리가 끝나는 시각을 알려 주는 디지털 시계가 있다.

훈제오리구이를 시작하는 시각과 오븐구이를 하는 데 필요한 시간이 분단위로 주어졌을 때, 오븐구이가 끝나는 시각을 계산하는 프로그램을 작성하시오.

#### 입력

첫째 줄에는 현재 시각이 나온다.

현재 시각은 시 A (0 ≤ A ≤ 23) 와 분 B (0 ≤ B ≤ 59)가 정수로 빈칸을 사이에 두고 순서대로 주어진다.

두 번째 줄에는 요리하는 데 필요한 시간 C (0 ≤ C ≤ 1,000)가 분 단위로 주어진다.

#### 출력

첫째 줄에 종료되는 시각의 시와 분을 공백을 사이에 두고 출력한다.

(단, 시는 0부터 23까지의 정수, 분은 0부터 59까지의 정수이다.

디지털 시계는 23시 59분에서 1분이 지나면 0시 0분이 된다.)

### 문제 풀이

```java
import java.util.Scanner;

class Main{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        int hour = scan.nextInt();
        int minute = scan.nextInt();
        int working_time = scan.nextInt();

        hour += (minute + working_time) / 60;
        hour %= 24;
        minute = (minute + working_time) % 60;

        System.out.print(hour + " " + minute);
    }
}
```

#### 풀이 설명

Scanner 객체를 생성하여 사용자로부터 입력을 받을 준비를 합니다.

scan.nextInt() 메서드를 사용하여 시간(hour), 분(minute), 작업 시간(working_time)을 입력받습니다.

현재 분(minute)과 작업 시간(working_time)의 합을 60으로 나누어 시간(hour)에 더합니다.

계산된 시간(hour)이 24 이상일 경우 24로 나눈 나머지 값으로 갱신하여 24시간 형식으로 유지합니다.

현재 분(minute)과 작업 시간(working_time)의 합을 60으로 나누어 그 나머지 값을 새로운 분(minute)으로 갱신합니다.

계산된 시간과 분을 출력합니다.

감사합니다!
