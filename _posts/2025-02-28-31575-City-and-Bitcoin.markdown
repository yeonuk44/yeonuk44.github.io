---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-31575-City-and-Bitcoin
title: Baekjun 31575, City and Bitcoin
# title: Baekjun 31575, City and Bitcoin
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
date: 2025-02-28 09:00:00 +0900
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

## 백준 14298번, Vote (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

A와 B는 특정 선거에서 경쟁하는 유일한 두 후보입니다.

우리는 여론조사를 통해 정확히 N명의 유권자가 A를 지지하고 정확히 M명의 유권자가 B를 지지한다는 것을 알고 있습니다.

또한 N이 M보다 크므로 A가 이길 것이라는 것도 알고 있습니다.

유권자들은 한 번에 한 명씩 투표소에 나타나며, 모든 가능한 (N + M)! 순서에서 균일하게 무작위로 선택된 순서로 나타납니다.

각 유권자가 투표를 한 후, 투표소 직원은 결과를 업데이트하고 지금까지 어느 후보가 승리했는지(있는 경우) 기록합니다.

(투표가 동점인 경우, 어느 후보도 승리한 것으로 간주되지 않습니다.)

A가 항상 선두를 유지할 확률은 얼마인가?

즉, A가 모든 투표에서 항상 이길 확률은 얼마인가?

#### 입력

입력은 테스트 케이스의 수인 정수 T를 포함하는 한 줄로 시작합니다.

각 테스트 케이스는 각각 A와 B를 지지하는 유권자의 수인 두 정수 N과 M을 포함하는 한 줄로 구성됩니다.

#### 제한

1 ≤ T ≤ 100.

0 ≤ M < N ≤ 10.

#### 출력

각 테스트 케이스에 대해 다음이 포함된 한 줄을 출력합니다.

Case #x: y. 여기서 는 x 테스트 케이스 번호(1부터 시작)이고, 는 y 모든 투표에서 A가 항상 이길 확률입니다.

y 정답의 y 절대오차 또는 상대오차가 10-6 이내이면 정답 으로 간주합니다.

### 문제 풀이

```java
import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws IOException{
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int T = Integer.parseInt(br.readLine());
        StringBuilder sb = new StringBuilder();

        for(int i = 1; i <= T; i++) {
            StringTokenizer st = new StringTokenizer(br.readLine());
            int N = Integer.parseInt(st.nextToken());
            int M = Integer.parseInt(st.nextToken());

            double p = (double) (N - M) / (N + M);
            sb.append(String.format("Case #%d: %.8f\n", i, p));
        }
        System.out.print(sb);
    }
}
```

#### 풀이 설명

이 코드는 특정 선거에서 A 후보가 항상 선두를 유지할 확률을 계산하는 프로그램입니다.

먼저 BufferedReader를 사용하여 입력을 빠르게 읽어오고 첫 번째 입력값을 읽어 정수 T에 저장하는데, 이는 테스트 케이스의 개수를 의미합니다.

이후 for문을 이용하여 i = 1부터 T까지 반복하면서 각 테스트 케이스를 처리합니다.

StringTokenizer를 사용하여 한 줄을 공백 기준으로 나누고 각각 N(A를 지지하는 유권자 수)과 M(B를 지지하는 유권자 수)로 변환합니다.

A가 항상 선두를 유지할 확률 p는 Ballot Theorem 공식을 활용하여 (N - M) / (N + M)으로 계산합니다.

여기서 N - M은 A가 B보다 앞서야 하는 차이를 나타내고 N + M은 전체 유권자 수를 의미하므로 이 확률은 A가 항상 선두를 유지할 확률을 의미합니다.

이후 String.format("Case #%d: %.8f\n", i, p)를 사용하여 문제에서 요구하는 출력 형식에 맞춘다.

"Case #%d"는 테스트 케이스 번호를 나타내고 "%.8f"는 소수점 8자리까지 확률 값을 출력하며 \n을 추가하여 줄바꿈을 한다.

그리고 StringBuilder를 활용하여 문자열을 누적한 후 System.out.print(sb)를 사용하여 한 번에 출력하는데 이렇게 하면 여러 번 System.out.println()을 호출하는 것보다 성능이 향상됩니다.

예제 입력 2 2 1 1 0이 주어졌을 때 첫 번째 테스트 케이스(2, 1)의 확률은 (2-1) / (2+1) = 1/3 = 0.33333333이 되고 두 번째 테스트 케이스(1, 0)의 확률은 (1-0) / (1+0) = 1/1 = 1.00000000이 됩니다.

각 테스트 케이스에서 N과 M을 입력받고 단순 연산을 수행하므로 O(1)의 시간 복잡도를 가지며 전체적으로 O(T)의 시간 복잡도를 가집니다.

T가 최대 100이고 N과 M의 최대값이 10이므로 매우 빠르게 실행된다.
