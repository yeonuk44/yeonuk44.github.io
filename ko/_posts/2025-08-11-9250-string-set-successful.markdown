---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-9250-string-set-successful
title: 백준 9250번, 문자열 집합 성공(with.Java)
# title: Baekjun 9250, string set successful (with.Java)
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
date: 2025-08-11 09:00:00 +0900
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

## 백준 9250번, 문자열 집합 성공(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

총 N개의 문자열로 이루어진 집합 S가 주어진다.

입력으로 주어지는 M개의 문자열 중에서 집합 S에 포함되어 있는 것이 총 몇 개인지 구하는 프로그램을 작성하시오.

#### 입력

첫째 줄에 문자열의 개수 N과 M (1 ≤ N ≤ 10,000, 1 ≤ M ≤ 10,000)이 주어진다.

다음 N개의 줄에는 집합 S에 포함되어 있는 문자열들이 주어진다.

다음 M개의 줄에는 검사해야 하는 문자열들이 주어진다.

입력으로 주어지는 문자열은 알파벳 소문자로만 이루어져 있으며, 길이는 500을 넘지 않는다.

합 S에 같은 문자열이 여러 번 주어지는 경우는 없다.

#### 출력

첫째 줄에 M개의 문자열 중에 총 몇 개가 집합 S에 포함되어 있는지 출력한다.

### 문제 풀이

```java
import java.util.*;
import java.io.*;

class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());
        int N = Integer.valueOf(st.nextToken());
        int M = Integer.valueOf(st.nextToken());
        HashSet<String> set = new HashSet<>();
        int count = 0;

        for(int i = 0; i < N; i++){
            set.add(br.readLine());
        }
        for(int i = 0; i < M; i++){
            String str = br.readLine();

            if(set.contains(str)){
                count++;
            }
        }

        System.out.print(count);
    }
}
```

#### 풀이 설명

이 코드는 두 개의 리스트에서 공통으로 존재하는 문자열의 개수를 찾는 프로그램입니다.

입력으로 주어지는 두 개의 리스트에서 중복되는 요소가 몇 개 있는지 계산하여 출력합니다.

먼저 BufferedReader와 StringTokenizer를 사용해 입력을 처리합니다.

첫 번째 줄에서 두 리스트의 크기인 N과 M을 입력받습니다.

그 다음 HashSet을 생성하여, 첫 번째 리스트의 요소들을 저장합니다.

HashSet은 중복을 허용하지 않으므로, 이 과정에서 중복된 요소는 자동으로 제거됩니다.

두 번째 리스트의 각 요소를 읽어오면서, 그 요소가 HashSet에 존재하는지 확인합니다.

존재하면 count를 증가시켜 중복된 요소의 수를 셉니다.

모든 비교가 끝나면 count를 출력하여, 두 리스트에서 공통으로 존재하는 문자열의 개수를 결과로 보여줍니다.

이 방법은 효율적이며, 두 리스트의 크기가 커도 빠르게 중복 요소를 확인할 수 있습니다.
