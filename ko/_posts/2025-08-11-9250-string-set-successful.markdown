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

## 백준 2776번, 암기왕 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

연종이는 엄청난 기억력을 가지고 있다.

그래서 하루 동안 본 정수들을 모두 기억 할 수 있다.

하지만 이를 믿을 수 없는 동규는 그의 기억력을 시험해 보기로 한다.

동규는 연종을 따라 다니며, 연종이 하루 동안 본 정수들을 모두 ‘수첩1’에 적어 놓았다.

그것을 바탕으로 그가 진짜 암기왕인지 알아보기 위해, 동규는 연종에게 M개의 질문을 던졌다.

질문의 내용은 “X라는 정수를 오늘 본 적이 있는가?” 이다.

연종은 막힘없이 모두 대답을 했고, 동규는 연종이 봤다고 주장하는 수 들을 ‘수첩2’에 적어 두었다.

집에 돌아온 동규는 답이 맞는지 확인하려 하지만, 연종을 따라다니느라 너무 힘들어서 여러분에게 도움을 요청했다.

동규를 도와주기 위해 ‘수첩2’에 적혀있는 순서대로, 각각의 수에 대하여, ‘수첩1’에 있으면 1을, 없으면 0을 출력하는 프로그램을 작성해보자.

#### 입력

첫째 줄에 테스트케이스의 개수 T가 들어온다.

다음 줄에는 ‘수첩 1’에 적어 놓은 정수의 개수 N(1 ≤ N ≤ 1,000,000)이 입력으로 들어온다.

그 다음 줄에 ‘수첩 1’에 적혀 있는 정수들이 N개 들어온다.

그 다음 줄에는 ‘수첩 2’에 적어 놓은 정수의 개수 M(1 ≤ M ≤ 1,000,000) 이 주어지고, 다음 줄에 ‘수첩 2’에 적어 놓은 정수들이 입력으로 M개 들어온다.

모든 정수들의 범위는 int 로 한다.

#### 출력

‘수첩2’에 적혀있는 M개의 숫자 순서대로, ‘수첩1’에 있으면 1을, 없으면 0을 출력한다.

### 문제 풀이

```java
import java.util.*;
import java.io.*;

class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringBuilder sb = new StringBuilder();

        int T = Integer.valueOf(br.readLine());
        for(int i = 0; i < T; i++){
            int N_len = Integer.valueOf(br.readLine());
            StringTokenizer st = new StringTokenizer(br.readLine(), " ");
            HashSet<String> set = new HashSet<>();
            for(int j = 0; j < N_len; j++){
                set.add(st.nextToken());
            }
            int M_len = Integer.valueOf(br.readLine());
            st = new StringTokenizer(br.readLine(), " ");

            for(int j = 0; j < M_len; j++){
                if(set.contains(st.nextToken())){
                    sb.append("1\n");
                }else{
                    sb.append("0\n");
                }
            }
        }
        System.out.print(sb.toString());
    }
}
```

#### 풀이 설명

이 코드는 주어진 두 리스트에서 공통 요소를 확인하는 프로그램입니다.

입력으로 주어지는 여러 테스트 케이스를 처리하며, 각 테스트 케이스마다 두 리스트를 비교하여 공통 요소가 있는지 확인하고 결과를 출력합니다.

프로그램은 먼저 입력을 받기 위해 BufferedReader와 StringBuilder를 사용합니다.

첫 번째 줄에서 테스트 케이스의 수 T를 입력받습니다. 이후 반복문을 통해 각 테스트 케이스를 처리합니다.

첫 번째 리스트의 길이 N_len을 입력받고, 해당 리스트의 요소들을 HashSet에 저장합니다.

HashSet은 중복을 허용하지 않기 때문에 리스트의 요소를 저장하는 데 적합합니다.

두 번째 리스트의 길이 M_len을 입력받고, 해당 리스트의 요소들을 하나씩 HashSet에 저장된 요소들과 비교합니다. 만약 요소가 HashSet에 존재하면 1을, 존재하지 않으면 0을 StringBuilder에 추가합니다. 각 결과는 개행 문자로 구분됩니다.

모든 테스트 케이스를 처리한 후, 최종 결과를 System.out.print를 사용하여 출력합니다. 이 접근 방식은 리스트의 요소들이 중복될 가능성이 없으며, 리스트가 크더라도 효율적으로 공통 요소를 찾을 수 있게 해줍니다.
