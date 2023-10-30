---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Many_Elements_Of_Array
title: 배열의 원소만큼 추가하기(with.Java)
# title: Add as many elements of an array (with.Java)
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
date: 2023-10-28 09:00:00 +0900
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

### 배열의 원소만큼 추가하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

아무 원소도 들어있지 않은 빈 배열 X가 있습니다.

양의 정수 배열 arr가 매개변수로 주어질 때, arr의 앞에서부터 차례대로 원소를 보면서 원소가 a라면 X의 맨 뒤에 a를 a번 추가하는 일을 반복한 뒤의 배열 X를 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| arr       | result                               |
| --------- | ------------------------------------ |
| [5, 1, 4] | [5, 5, 5, 5, 5, 1, 4, 4, 4, 4]       |
| [6, 6]    | [6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6] |
| [1]       | [1]                                  |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] arr) {
        int length = 0;
        for(int i = 0; i < arr.length; i++){
            length += arr[i];
        }
        int[] answer = new int[length];
        int idx = 0;
        for(int i = 0; i < arr.length; i++){
            for(int j = 0; j < arr[i]; j++){
                answer[idx++] =  arr[i];
            }
        }
        return answer;
    }
}
```

##### 풀이 설명

주어진 코드는 입력으로 주어진 정수 배열 arr에 있는 각 요소를 해당 요소의 값만큼 복제하여 새로운 배열 answer를 생성하고 반환하는 함수입니다. 코드를 간략하게 설명하겠습니다.

int length = 0;: 새로운 배열 answer의 길이를 결정하기 위한 변수 length를 초기화합니다.

첫 번째 반복문(for(int i = 0; i < arr.length; i++)): 입력 배열 arr을 반복하여 각 요소의 값을 더하여 length 변수에 저장합니다. 이렇게 함으로써 answer 배열의 전체 길이를 결정합니다.

int[] answer = new int[length];: length 변수를 기반으로 한 길이를 가진 새로운 정수 배열 answer를 생성합니다.

int idx = 0;: answer 배열에 값을 할당할 인덱스를 추적하는 변수 idx를 초기화합니다.

두 번째 반복문(for(int i = 0; i < arr.length; i++) 내부의 for(int j = 0; j < arr[i]; j++)): arr 배열을 다시 반복하고, 각 요소의 값(arr[i])만큼 반복하면서 해당 요소를 answer 배열에 복제합니다.

이를 통해 요소의 값이 2인 경우 해당 요소가 answer 배열에 두 번 나타납니다.

return answer;: 최종적으로 생성된 answer 배열을 반환합니다.
