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

### n개 간격의 원소들(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 리스트 num_list와 정수 n이 주어질 때, num_list의 첫 번째 원소부터 마지막 원소까지 n개 간격으로 저장되어있는 원소들을 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

##### 입출력 예시

num_list: [4, 2, 6, 1, 7, 6]

n: 2

result: [4, 6, 7]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int answerLength = (int) Math.ceil((double) num_list.length / n);
        int[] answer = new int[answerLength];

        for (int i = 0; i < num_list.length; i += n) {
            int index = i / n;
            answer[index] = num_list[i];
        }

        return answer;
    }
}
```

##### 풀이 설명

int answerLength = (int) Math.ceil((double) num_list.length / n);:

이 부분에서는 새로운 배열 answer의 길이를 계산합니다.

num_list.length는 입력 배열 num_list의 길이를 나타냅니다.

n은 주어진 간격입니다.

이를 나누고 올림 연산을 수행하여 나머지 원소들까지 빠짐없이 배열에 담을 수 있도록 길이를 설정합니다.

int[] answer = new int[answerLength];:

계산된 answerLength를 기반으로 answer 배열을 생성합니다.

이 배열은 결과적으로 num_list에서 추출한 원소들을 담을 배열입니다.

for (int i = 0; i < num_list.length; i += n) {:

이 부분은 반복문으로, 입력 배열 num_list를 탐색하면서 간격 n마다 원소를 추출합니다.

반복문을 시작하면서 i는 0부터 시작합니다.

int index = i / n;:

원소를 answer 배열에 저장할 인덱스를 계산합니다.

현재 i는 num_list의 인덱스를 나타내며, n 간격마다 저장해야 하므로 index를 계산합니다.

index는 answer 배열에서의 인덱스를 나타냅니다.

answer[index] = num_list[i];:

계산된 index를 이용하여 num_list에서 추출한 원소를 answer 배열에 저장합니다.

i 인덱스에 위치한 원소를 추출하여 answer 배열의 index 위치에 저장합니다.

return answer;:

반복문을 모두 실행한 뒤, answer 배열에는 num_list에서 간격 n마다 추출한 원소가 저장되어 있습니다.

최종적으로 answer 배열을 반환하여 결과를 출력합니다.

이 코드는 입력 배열 num_list에서 간격 n마다 원소를 추출하여 answer 배열에 저장하는 작업을 수행합니다. 이를 통해 answer 배열에는 입력 배열에서 원하는 간격으로 추출한 원소들이 순서대로 담겨있게 됩니다.열을 반환하는 기능을 수행합니다.
