---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_List_Truncation
title: 리스트 자르기, 주어진 정수와 리스트에 대해 자르고 배열에 할당하는 방법에 대하여(with.Java)
# title: List Truncation, how to truncate and assign to an array for a given integer and list (with.Java)

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
date: 2023-09-21 09:00:00 +0900
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

### 카운트 다운(with.Java)

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 start_num와 end_num가 주어질 때, start_num에서 end_num까지 1씩 감소하는 수들을 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

##### 입출력 예시

| start_num | end_num | result                    |
| --------- | ------- | ------------------------- |
| 10        | 3       | [10, 9, 8, 7, 6, 5, 4, 3] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
import java.util.ArrayList;
import java.util.List;

public class Solution {
    public static void main(String[] args) {
        int start_num = 10;
        int end_num = 5;
        List<Integer> result = solution(start_num, end_num);
        System.out.println(result);
    }

    public static List<Integer> solution(int start_num, int end_num) {
        List<Integer> result = new ArrayList<>();

        for (int i = start_num; i >= end_num; i--) {
            result.add(i);
        }

        return result;
    }
}

```

##### 풀이 설명

int start_num = 10;과 int end_num = 5;: 시작 숫자 start_num은 10으로, 종료 숫자 end_num은 5로 초기화합니다.

List<Integer> result = solution(start_num, end_num);: solution 함수를 호출하여 시작 숫자부터 종료 숫자까지의 숫자들을 리스트에 저장한 후, 이를 result 변수에 할당합니다.

System.out.println(result);: 리스트에 저장된 숫자들을 출력합니다.

public static List<Integer> solution(int start_num, int end_num) : solution 함수는 시작 숫자 start_num과 종료 숫자 end_num을 입력으로 받아서, 시작 숫자부터 종료 숫자까지의 숫자들을 저장한 리스트를 반환합니다.

List<Integer> result = new ArrayList<>();: 결과를 저장할 정수 리스트 result를 생성합니다.

for (int i = start_num; i >= end_num; i--) : 시작 숫자부터 종료 숫자까지 감소하는 반복문을 실행합니다.

result.add(i);: 각 숫자 i를 리스트 result에 추가합니다.

return result;: 시작 숫자부터 종료 숫자까지의 숫자들이 저장된 리스트 result를 반환합니다.

이 코드는 시작 숫자부터 종료 숫자까지의 숫자를 역순으로 리스트에 저장하고, 그 리스트를 출력합니다.
