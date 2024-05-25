---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Of_K
title: k의 개수 (with.Java)
# title: Number of k (with.Java)
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
date: 2024-05-25 09:00:00 +0900
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

## "k의 개수 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

1부터 13까지의 수에서, 1은 1, 10, 11, 12, 13 이렇게 총 6번 등장합니다.

정수 i, j, k가 매개변수로 주어질 때, i부터 j까지 k가 몇 번 등장하는지 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ i < j ≤ 100,000
- 0 ≤ k ≤ 9

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

<!-- | before  | after   | result |
| ------- | ------- | ------ |
| "olleh" | "hello" | 1      |
| "allpe" | "apple" | 0      | -->

| i   | j   | k   | result |
| --- | --- | --- | ------ |
| 1   | 13  | 1   | 6      |
| 10  | 50  | 5   | 5      |
| 3   | 10  | 2   | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int i, int j, int k) {
        int answer = 0;
        String str = "0";
        char ch = '0';
        for(int a = i; a <= j; a++){
            str = Integer.toString(a);
            for(int b = 0; b < str.length(); b++){
                ch = str.charAt(b);
                if(ch == Integer.toString(k).charAt(0)){
                    answer++;
                }
            }
        }
        return answer;
    }
}
```

### 풀이 리뷰

answer 변수를 초기값 0으로 설정합니다.

이 변수는 결과를 나타냅니다.

str 변수를 "0"으로 초기화합니다. 이 변수는 숫자를 문자열로 변환하여 저장하는 용도로 사용됩니다.

ch 변수를 '0'으로 초기화합니다. 이 변수는 문자열에서 한 문자씩 확인하기 위해 사용됩니다.

a 변수를 i부터 j까지 증가시키면서 반복문을 실행합니다.

a 값을 문자열로 변환하여 str 변수에 저장합니다.

b 변수를 0부터 str의 길이-1까지 증가시키면서 반복문을 실행합니다.

str의 b번째 문자(ch)를 확인합니다.

ch가 k와 같다면, answer 변수를 1 증가시킵니다.

반복문이 종료되면 answer 변수를 반환합니다.

해당 코드는 입력받은 범위 내에서 각 숫자를 문자열로 변환하고, 문자열의 각 문자를 하나씩 확인하여 k와 비교하는 방식으로 구현되어 있습니다.
