---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-buffered-lighters-vs-system-out-println-performance-comparison
title: Buffered Lighters vs. System.out.println() Performance Comparison
# title: Buffered Lighters vs. System.out.println() Performance Comparison
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
date: 2025-03-12 09:00:00 +0900
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

## 백준 1546번, 평균 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

세준이는 기말고사를 망쳤다.

세준이는 점수를 조작해서 집에 가져가기로 했다.

일단 세준이는 자기 점수 중에 최댓값을 골랐다.

이 값을 M이라고 한다. 그리고 나서 모든 점수를 점수/M\*100 으로 고쳤다.

예를 들어, 세준이의 최고점이 70이고, 수학점수가 50이었으면 수학점수는 50/70\*100이 되어 71.43점이 된다.

세준이의 성적을 위의 방법대로 새로 계산했을 때, 새로운 평균을 구하는 프로그램을 작성하시오.

#### 입력

첫째 줄에 시험 본 과목의 개수 N이 주어진다.

이 값은 1000보다 작거나 같다. 둘째 줄에 세준이의 현재 성적이 주어진다.

이 값은 100보다 작거나 같은 음이 아닌 정수이고, 적어도 하나의 값은 0보다 크다.

#### 출력

첫째 줄에 새로운 평균을 출력한다.

실제 정답과 출력값의 절대오차 또는 상대오차가 10-2 이하이면 정답이다.

### 문제 풀이

```java
import java.io.*;
import java.util.*;

class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        ArrayList<Integer> list = new ArrayList<>();
        float high_score = 0;
        float avg_score = 0;
        br.readLine();

        StringTokenizer st = new StringTokenizer(br.readLine());
        while (st.hasMoreTokens()) {

            list.add(Integer.valueOf(st.nextToken()));
        }

        for(int i = 0; i < list.size(); i++) {
            if(high_score <= list.get(i)){
                high_score = list.get(i);
            }
        }

        for(int i = 0; i < list.size(); i++) {
            avg_score += list.get(i)/high_score*100;
        }

        bw.write(avg_score/list.size() + "\n");
        br.close();
        bw.flush();
        bw.close();
    }
}
```

#### 풀이 설명

먼저, `BufferedReader`를 사용해 입력을 받고, `ArrayList<Integer>`를 활용해 점수 리스트를 저장합니다.

첫 번째 입력 줄은 사용하지 않으며, 두 번째 줄에서 공백으로 구분된 점수들을 `StringTokenizer`를 이용해 분리하여 리스트에 추가합니다.

그 후, 리스트를 순회하면서 최고 점수를 찾습니다.

처음 설정된 `high_score` 값은 0이며, 리스트의 각 값을 비교해 가장 높은 값을 저장합니다.

다음으로, 새로운 평균을 계산하는 과정이 있습니다.

각 점수를 최고 점수로 나눈 뒤 100을 곱하여 변환된 점수를 구하고, 이 값들을 모두 합한 후 리스트 크기로 나누어 최종 평균을 계산합니다.

마지막으로, `BufferedWriter`를 사용해 평균을 출력하고, `br.close()`, `bw.flush()`, `bw.close()`를 통해 입력 및 출력 스트림을 정리합니다.

이 코드에서 주의할 점은 `high_score`가 0인 경우 나눗셈 연산에서 `ArithmeticException`이 발생할 수 있다는 점입니다.

따라서 `high_score`를 찾는 과정에서 제대로 값을 갱신하도록 해야 합니다.

또한, 연산 정확도를 높이기 위해 리스트의 타입을 `Float`로 변경하면 더 안정적인 결과를 얻을 수 있습니다.

출력 형식은 소수점 자리수를 조정하여 가독성을 높일 수 있으며, 이를 위해 `String.format("%.2f")`를 사용할 수 있습니다.

개선한 코드도 작성해보았습니다. 참고가 되었으면 합니다.

```java
import java.io.*;
import java.util.*;

class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        ArrayList<Float> list = new ArrayList<>();
        float high_score = 0;
        float avg_score = 0;
        br.readLine();

        StringTokenizer st = new StringTokenizer(br.readLine());
        while (st.hasMoreTokens()) {
            list.add(Float.valueOf(st.nextToken()));
        }

        for(float score : list) {
            if(score > high_score){
                high_score = score;
            }
        }

        for(float score : list) {
            avg_score += score/high_score*100;
        }

        bw.write(avg_score/list.size() + "\n");
        br.close();
        bw.flush();
        bw.close();
    }
}
```
