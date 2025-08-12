---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-1764-listen-and-unheard
title: 백준 1764번, 듣보잡 (with.Java)
# title: Baekjun, 1764, "With. Java"
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
date: 2025-08-12 09:00:00 +0900
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

## 백준 1764번, 듣보잡 (with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

김진영이 듣도 못한 사람의 명단과, 보도 못한 사람의 명단이 주어질 때, 듣도 보도 못한 사람의 명단을 구하는 프로그램을 작성하시오.

#### 입력

첫째 줄에 듣도 못한 사람의 수 N, 보도 못한 사람의 수 M이 주어진다.

이어서 둘째 줄부터 N개의 줄에 걸쳐 듣도 못한 사람의 이름과, N+2째 줄부터 보도 못한 사람의 이름이 순서대로 주어진다.

이름은 띄어쓰기 없이 알파벳 소문자로만 이루어지며, 그 길이는 20 이하이다. N, M은 500,000 이하의 자연수이다.

듣도 못한 사람의 명단에는 중복되는 이름이 없으며, 보도 못한 사람의 명단도 마찬가지이다.

#### 출력

듣보잡의 수와 그 명단을 사전순으로 출력한다.

### 문제 풀이

```java
import java.util.*;
import java.io.*;

class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());
        HashSet<String> N = new HashSet<>();
        ArrayList<String> answer = new ArrayList<>();
        int N_len = Integer.valueOf(st.nextToken());
        int M = Integer.valueOf(st.nextToken());
        for(int i = 0; i < N_len; i++){
            N.add(br.readLine());
        }
        for(int i = 0; i < M; i++){
            String temp = br.readLine();
            if(N.contains(temp)){
                answer.add(temp);
            }
        }
        int answer_len = answer.size();
        System.out.println(answer_len);
        Collections.sort(answer);
        for(int i = 0; i < answer_len; i++){
            System.out.println(answer.get(i));
        }
    }
}
```

#### 풀이 설명

이 코드는 두 개의 리스트에서 공통으로 존재하는 문자열을 찾아 출력하는 프로그램입니다.

주어진 두 리스트에서 공통된 요소를 먼저 찾아낸 후, 이를 사전순으로 정렬하여 출력합니다.

프로그램은 먼저 HashSet과 ArrayList를 사용하여 입력을 처리합니다.

첫 번째 리스트에서 입력된 문자열을 HashSet에 저장합니다.

HashSet은 내부적으로 해시맵을 사용하여 데이터를 저장하므로, 특정 요소가 집합에 존재하는지 확인하는 contains() 메서드는 평균적으로 O(1)의 시간 복잡도를 가집니다.

이는 매우 효율적이며, 특히 요소의 수가 많을 때 성능상의 이점을 제공합니다.

그 다음, 두 번째 리스트의 각 요소를 순차적으로 읽어오며, 해당 요소가 HashSet에 존재하는지 확인합니다.

존재한다면, 이 요소를 ArrayList에 추가합니다.

ArrayList는 순차적으로 데이터를 저장하며, 특정 요소가 리스트에 포함되어 있는지 확인하는 contains() 메서드는 내부적으로 indexOf()를 사용해 순차적으로 탐색하므로, O(n)의 시간 복잡도를 가집니다.

이 코드에서는 ArrayList를 중복된 요소를 수집하고 출력하는 용도로 사용하였고, 이는 HashSet을 사용해 요소를 필터링한 후에 정렬된 결과를 출력하기 위한 적절한 선택입니다.

마지막으로, ArrayList에 저장된 공통 요소를 Collections.sort()를 통해 사전순으로 정렬합니다.

정렬된 결과를 출력하기 전에 공통 요소의 개수를 출력하고, 이후 각 요소를 순서대로 출력합니다.

초기에는 ArrayList를 사용해 중복 요소를 찾는 방식으로 접근할 수 있었으나, 이 경우 시간 복잡도가 높아져 비효율적이었습니다.

HashSet을 사용함으로써 효율성을 크게 개선할 수 있었으며, 이는 특히 입력 데이터의 크기가 클 때 중요한 최적화입니다.
