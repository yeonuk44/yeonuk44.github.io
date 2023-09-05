---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_Counting_Up
title: 카운트 업 구현에 대하여(with.Java)
# title: About implementing counting up (with.Java)

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
date: 2023-09-05 09:00:00 +0900
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

### 카운트 업 구현에 대하여(with.Java) 알아본 글입니다.

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.
문제에 대해 먼저 알아보겠습니다.

#### 문제

모든 자연수 x에 대해서 현재 값이 x이면 x가 짝수일 때는 2로 나누고, x가 홀수일 때는 3 \* x + 1로 바꾸는 계산을 계속해서 반복하면 언젠가는 반드시 x가 1이 되는지 묻는 문제를 콜라츠 문제라고 부릅니다.
그리고 위 과정에서 거쳐간 모든 수를 기록한 수열을 콜라츠 수열이라고 부릅니다.
계산 결과 1,000 보다 작거나 같은 수에 대해서는 전부 언젠가 1에 도달한다는 것이 알려져 있습니다.
임의의 1,000 보다 작거나 같은 양의 정수 n이 주어질 때 초기값이 n인 콜라츠 수열을 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

n: 10
result: [10, 5, 16, 8, 4, 2, 1]

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int[] solution(int n) {
        ArrayList<Integer> temp = new ArrayList<Integer>();
        temp.add(n);

        while(n != 1){
            if(n % 2 == 0){
                n = n / 2;
            } else {
                n = 3 * n + 1;
            }
            temp.add(n);
        }

        int[] answer = new int[temp.size()];
        for(int i = 0; i < temp.size(); i++){
            answer[i] = temp.get(i);
        }

        return answer;
    }
}
```

##### 풀이 설명

ArrayList<Integer> temp = new ArrayList<Integer>();: 정수를 저장할 ArrayList 객체 temp를 생성합니다.
temp.add(n);: 초기 정수 n을 temp 리스트에 추가합니다. 이 리스트는 추측 과정의 모든 값을 저장할 예정입니다.
while(n != 1): n이 1이 될 때까지 반복하는 루프를 시작합니다. Collatz 추측에 따라 n을 변환하고, n이 1이 되면 루프를 종료합니다.
if(n % 2 == 0): n이 짝수인지 확인합니다. 짝수인 경우, n을 2로 나눠 홀수로 만듭니다.
else { n = 3 \* n + 1; }: n이 홀수인 경우, n에 3을 곱하고 1을 더해 짝수로 만듭니다.
temp.add(n);: 변환된 n 값을 temp 리스트에 추가합니다.
int[] answer = new int[temp.size()];: temp 리스트의 크기에 맞는 정수 배열 answer를 생성합니다.
for(int i = 0; i < temp.size(); i++){ answer[i] = temp.get(i); }: temp 리스트의 값을 배열 answer에 복사합니다.
return answer;: Collatz 추측 결과가 저장된 배열 answer를 반환합니다.
