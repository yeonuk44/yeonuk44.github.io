---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Determinig_Finite_Decimal_Numbers
title: 유한소수 판별하기(with.Java)
# title: Determining finite decimal numbers (with.Java)
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
date: 2024-05-16 09:00:00 +0900
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

## "유한소수 판별하기(with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

소수점 아래 숫자가 계속되지 않고 유한개인 소수를 유한소수라고 합니다.

분수를 소수로 고칠 때 유한소수로 나타낼 수 있는 분수인지 판별하려고 합니다.

유한소수가 되기 위한 분수의 조건은 다음과 같습니다.

기약분수로 나타내었을 때, 분모의 소인수가 2와 5만 존재해야 합니다.

두 정수 a와 b가 매개변수로 주어질 때, a/b가 유한소수이면 1을, 무한소수라면 2를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- a, b는 정수
- 0 < a ≤ 1,000
- 0 < b ≤ 1,000

#### 입출력 예시

<!-- | lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| a   | b   | result |
| --- | --- | ------ |
| 7   | 20  | 1      |
| 11  | 22  | 1      |
| 12  | 21  | 2      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int a, int b) {
        int answer = 0;
        int temp = b / GCD(a, b);

        while(temp != 1){
            if(temp % 2 == 0){
                temp /= 2;
            }else if(temp % 5 == 0){
                temp /= 5;
            }else {
                answer = 2;
                return answer;
            }
        }

        answer = 1;

        return answer;
    }

    private int GCD(int a, int b){
            if(b == 0){
                return a;
            }else{
                return GCD(b, a % b);
            }
        }
}
```

### 풀이 설명

변수 temp에 b를 a와 b의 최대공약수(GCD)로 나눈 값을 저장합니다.

이를 위해 GCD 메서드를 호출합니다.

temp가 1이 될 때까지 반복문을 수행합니다.

temp를 2 또는 5로 나누어 떨어지는지 확인합니다.

만약 나누어 떨어진다면 해당 값을 각각 2와 5로 나눈 후, 다시 temp를 갱신합니다.

만약 temp가 2 또는 5로 나누어 떨어지지 않는다면, answer를 2로 설정하고, 이 값을 반환합니다.

모든 조건을 통과한 경우, answer를 1로 설정하고, 이 값을 반환합니다.

이 코드는 주어진 두 수의 관계를 파악하여 효율적으로 문제를 해결합니다.

특히, 최대공약수를 활용하여 나누어 떨어지는지를 판별하는 점이 해결 방법의 핵심입니다.
