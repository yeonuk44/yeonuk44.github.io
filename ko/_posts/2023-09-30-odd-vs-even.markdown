---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Odd_Vs_Even
title: 홀수 vs 짝수(with.Java)
# title: Odd vs. Even (with.Java)

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
date: 2023-09-30 09:00:00 +0900
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

### 홀수 vs 짝수(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 리스트 num_list가 주어집니다.

가장 첫 번째 원소를 1번 원소라고 할 때, 홀수 번째 원소들의 합과 짝수 번째 원소들의 합 중 큰 값을 return 하도록 solution 함수를 완성해주세요.

두 값이 같을 경우 그 값을 return합니다.

##### 입출력 예시

| num_list           | result |
| ------------------ | ------ |
| [4, 2, 6, 1, 7, 6] | 17     |
| [-1, 2, 5, 6, 3]   | 8      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
        int oddSum = 0;
        int evenSum = 0;
        for(int i = 0; i < num_list.length; i++){
            if(i % 2 == 0){
                evenSum += num_list[i];
            }else {
                oddSum += num_list[i];
            }
        }
        answer = evenSum >= oddSum ? evenSum : oddSum;
        return answer;
    }
}
```

##### 풀이 설명

int answer = 0;: 결과를 저장할 변수 answer를 초기화합니다.

int oddSum = 0;, int evenSum = 0;: 짝수 인덱스에 있는 요소들과 홀수 인덱스에 있는 요소들을 합산할 변수 oddSum과 evenSum을 초기화합니다.

for(int i = 0; i < num_list.length; i++) : 입력 배열 num_list를 반복하면서 각 요소를 검사합니다.

if(i % 2 == 0) : 현재 인덱스 i가 짝수인 경우:

evenSum에 현재 요소 값을 더합니다.

else : 현재 인덱스 i가 홀수인 경우:

oddSum에 현재 요소 값을 더합니다.

answer = evenSum >= oddSum ? evenSum : oddSum;: 짝수 인덱스에 있는 요소들의 합 evenSum과 홀수 인덱스에 있는 요소들의 합 oddSum을 비교하여, 더 큰 합을 answer에 저장합니다.

return answer;: 최종적으로 두 합 중 더 큰 값을 반환합니다.
