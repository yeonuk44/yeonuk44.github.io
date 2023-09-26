---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Starting_With_The_n_th_Element
title: n 번째 원소부터, 정수리스트에서 정수 n번째 원소부터 마지막 원소까지의 새로운 리스트를 반환하는 방법에 대하여(with.Java)
# title: Starting with the n th element (with.Java)

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
date: 2023-09-26 09:00:00 +0900
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

### n 번째 원소부터, 정수리스트에서 정수 n번째 원소부터 마지막 원소까지의 새로운 리스트를 반환하는 방법에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 리스트 num_list와 정수 n이 주어질 때, n 번째 원소부터 마지막 원소까지의 모든 원소를 담은 리스트를 return하도록 solution 함수를 완성해주세요.

##### 입출력 예시

num_list: [2, 1, 6]

n: 3

result: [6]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer =  new int[num_list.length - n + 1];
        for(int i = n - 1; i < num_list.length; i++){
            answer[i - n + 1] = num_list[i];
        }
        return answer;
    }
}
```

##### 풀이 설명

Solution 클래스 내부에 있는 solution 메서드는 두 개의 매개변수를 받습니다.

첫 번째 매개변수는 num_list라는 정수 배열이고, 두 번째 매개변수는 n이라는 정수입니다.

배열 크기 정의: num_list의 n 번째 원소부터 마지막 원소까지의 길이를 계산하여 answer라는 새로운 배열의 크기를 지정합니다.

배열의 크기는 num_list.length - n + 1이 됩니다.

반복문을 통한 복사: for 반복문을 사용하여 n 번째 원소부터 마지막 원소까지 num_list의 값을 answer 배열에 복사합니다.

i 변수는 n - 1부터 시작하여 num_list.length보다 작을 때까지 반복하며, 이렇게 하면 Java에서의 0 기반 인덱싱을 처리할 수 있습니다.

결과 반환: 복사가 완료되면, answer 배열을 반환합니다. 이 배열은 num_list의 n 번째 원소부터 마지막 원소까지의 값을 담고 있습니다.
