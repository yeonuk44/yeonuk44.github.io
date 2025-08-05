---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-2751-sorting-numbers-2
title: 백준 2751번, 수 정렬하기 2 (with.Java)
# title: Baekjoon Problem 2751, Sorting Numbers 2 (with.Java)
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
date: 2025-08-03 09:00:00 +0900
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

## 백준 2751번, 수 정렬하기 2 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

N개의 수가 주어졌을 때, 이를 오름차순으로 정렬하는 프로그램을 작성하시오.

#### 입력

첫째 줄에 수의 개수 N(1 ≤ N ≤ 1,000,000)이 주어진다.

둘째 줄부터 N개의 줄에는 수가 주어진다.

이 수는 절댓값이 1,000,000보다 작거나 같은 정수이다.

수는 중복되지 않는다.

#### 출력

첫째 줄부터 N개의 줄에 오름차순으로 정렬한 결과를 한 줄에 하나씩 출력한다.

### 문제 풀이

```java
import java.util.PriorityQueue;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.BufferedWriter;
import java.io.OutputStreamWriter;
import java.io.IOException;

class Main{
    public static void main(String[] args) throws IOException {
        PriorityQueue<Integer> queue = new PriorityQueue<>();
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        int len = Integer.valueOf(br.readLine().trim());

        for(int i = 0; i < len; i++){
            queue.offer(Integer.valueOf(br.readLine().trim()));
        }
        br.close();

        while(!queue.isEmpty()){
            bw.write(String.valueOf(queue.poll()));
            if(!queue.isEmpty()){
                bw.newLine();
            }
        }
        bw.flush();
        bw.close();
    }
}
```

#### 풀이 설명

먼저 PriorityQueue를 사용하여 정수를 저장합니다.

입력을 받기 위해 BufferedReader를 사용하고, 출력을 위해 BufferedWriter를 사용합니다.

입력받은 첫 줄은 수의 개수를 나타내며, 이를 len 변수에 저장합니다.

이후 반복문을 통해 각 수를 입력받아 queue에 추가합니다.

모든 수를 입력받은 후, PriorityQueue에 저장된 수를 하나씩 꺼내어 BufferedWriter를 사용해 출력합니다.

각 수를 출력할 때마다 줄바꿈을 추가하여 형식을 맞춥니다.

마지막으로 BufferedWriter를 플러시하고 닫아 프로그램을 종료합니다.

이 프로그램은 효율적으로 수를 입력받고 정렬하여 출력하는 기능을 제공합니다.

감사합니다!
