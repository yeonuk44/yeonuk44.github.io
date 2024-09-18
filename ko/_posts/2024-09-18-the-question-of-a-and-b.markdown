---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Question_Of_Dividing_A_And_B
title: 백준 1008번, A/B 문제 (with.Java)
# title: Baekjun 1000, The question of dividing A and B
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
date: 2024-09-18 09:00:00 +0900
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

## 백준 1008번, A/B 문제 (with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.

#### 입력

첫째 줄에 A와 B가 주어진다. (0 < A, B < 10)

#### 출력

첫째 줄에 A+B를 출력한다.

#### 문제 풀이

사용자로부터 두 개의 정수를 입력받고, 그 합을 출력합니다.

이를 위해 Scanner 클래스를 사용하여 입력을 처리하고, 결과를 출력합니다.

### 문제에 대한 나의 풀이

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in); // Scanner 객체를 생성하여 입력을 받음
        int a = scan.nextInt(); // 첫 번째 정수를 입력받아 변수 a에 저장
        int b = scan.nextInt(); // 두 번째 정수를 입력받아 변수 b에 저장
        System.out.print(a + b); // a와 b의 합을 출력
        scan.close(); // Scanner 객체를 닫아 시스템 리소스를 해제
    }
}
```

#### 풀이 설명

문제를 풀며 Scanner 객체를 닫는 것에 대해 좀 더 알아보았습니다.

Scanner 객체를 닫지 않으면, 프로그램이 종료될 때까지 리소스가 해제되지 않을 수 있습니다.

이는 메모리 누수로 이어질 수 있으며, 특히 장시간 실행되는 프로그램에서는 시스템 리소스를 낭비할 수 있습니다.

### 결론

이 간단한 프로그램을 통해 Java에서 사용자 입력을 받아 처리하는 방법을 배웠습니다.

Scanner 클래스를 사용하여 입력을 받고, 이를 처리한 후 결과를 출력하는 방법을 이해하는 것은 Java 프로그래밍의 기본입니다.

또한, 사용한 시스템 리소스를 적절히 해제하기 위해 scan.close()를 사용하는 것도 잊지 마세요.

감사합니다!
