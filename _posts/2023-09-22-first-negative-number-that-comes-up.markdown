---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_First_Negative_Number_That_Comes_Up
title: The first negative number that comes up (with.Java)
# title: The first negative number that comes up (with.Java)

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
date: 2023-09-22 09:00:00 +0900
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

### 리스트 자르기, 주어진 정수와 리스트에 대해 자르고 배열에 할당하는 방법에 대하여(with.Java)

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 n과 정수 3개가 담긴 리스트 slicer 그리고 정수 여러 개가 담긴 리스트 num_list가 주어집니다. slicer에 담긴 정수를 차례대로 a, b, c라고 할 때, n에 따라 다음과 같이 num_list를 슬라이싱 하려고 합니다.

n = 1 : num_list의 0번 인덱스부터 b번 인덱스까지

n = 2 : num_list의 a번 인덱스부터 마지막 인덱스까지

n = 3 : num_list의 a번 인덱스부터 b번 인덱스까지

n = 4 : num_list의 a번 인덱스부터 b번 인덱스까지 c 간격으로

올바르게 슬라이싱한 리스트를 return하도록 solution 함수를 완성해주세요.

##### 입출력 예시

n: 3

slicer: [1,5,2]

num_list: [1,2,3,4,5,6,7,8,9]

result: [2,3,4,5,6]

[1, 2, 3, 4, 5, 6, 7, 8, 9]에서 1번 인덱스부터 5번 인덱스까지 자른 리스트는 [2, 3, 4, 5, 6]입니다.

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int n, int[] slicer, int[] num_list) {
        int[] arr = {};
        int a = slicer[0], b = slicer[1], c = slicer[2];
        if(n == 1){
            arr = new int[b + 1];
            for(int i = 0; i <= b; i++) {
                arr[i] = num_list[i];
            }
        } else if(n == 2){
            arr = new int[num_list.length - a];
            for(int i = a; i < num_list.length; i++) {
                arr[i - a] = num_list[i];
            }
        } else if(n == 3){
            arr = new int[b - a + 1];
            for(int i = a; i <= b; i++) {
                arr[i - a] = num_list[i];
            }
        } else if(n == 4){
            arr = new int[(b - a) / c + 1];
            for(int i = a; i <= b; i += c) {
                arr[(i - a) / c] = num_list[i];
            }
        }
        return arr;
    }
}
```

##### 풀이 설명

a, b, c는 slicer 리스트의 값을 차례로 받아 사용됩니다.

n = 1 인 경우:
num_list의 첫 번째 요소부터 b번째 요소까지를 포함한 새로운 배열을 생성합니다.

n = 2 인 경우:
num_list의 a번째 요소부터 마지막 요소까지를 포함한 새로운 배열을 생성합니다.

n = 3 인 경우:
num_list의 a번째 요소부터 b번째 요소까지를 포함한 새로운 배열을 생성합니다.

n = 4 인 경우:
num_list의 a번째 요소부터 b번째 요소까지 c 간격으로 요소를 선택하여 포함한 새로운 배열을 생성합니다.

결과 반환:
위의 조건에 따라 생성된 새로운 배열을 반환합니다.

즉, 이 코드는 n과 slicer에 따라 num_list를 다양한 방식으로 잘라내는 작업을 수행하며, 그 결과로 잘라낸 새로운 배열을 반환합니다.

다른 풀이법도 있어 제 코드와의 장단점도 비교해보겠습니다.

###### 다른 풀이법

```java
import java.util.*;
class Solution {
    public int[] solution(int n, int[] slicer, int[] num_list) {
        List<Integer> list = new ArrayList<>();
        int a = slicer[0];
        int b = slicer[1];
        int c = slicer[2];
        if(n == 1) {
            for(int i =0; i<b+1; i++) {
                list.add(num_list[i]);
            }
        }else if(n == 2) {
            for(int i = a; i<num_list.length; i++) {
                list.add(num_list[i]);
            }
        }else if(n ==3) {
            for(int i = a; i<b+1; i++) {
                list.add(num_list[i]);
            }
        }else if(n == 4) {
            for(int i = a; i<b+1; i+=c) {
                list.add(num_list[i]);

            }
        }
        int[] answer = list.stream().mapToInt(x -> x).toArray();
        return answer;
    }
}
```

새로 제시된 코드:
장점:유연성: ArrayList를 사용하므로 배열의 크기를 미리 지정할 필요가 없고, 동적으로 요소를 추가할 수 있어 코드가 더 간결하고 유연합니다.
가독성: 더 적은 변수와 명확한 로직으로 이해하기 쉽습니다.
단점:효율성: ArrayList와 스트림 연산을 사용하므로 원시 배열을 사용하는 것보다 약간 더 많은 시간과 메모리를 소모할 수 있습니다.

원래 코드:
장점:효율성: 원시 배열을 사용하므로 메모리와 시간 복잡도가 더 낮을 수 있습니다.
단점:복잡성: 배열의 크기를 미리 지정해야 하므로 코드가 조금 더 복잡해집니다. n에 따른 각 경우마다 배열의 크기를 따로 계산해야 합니다.

결론
새로 제시된 코드는 가독성과 유연성 측면에서 좋은 점이 있으나, 큰 데이터셋의 경우 원래 코드가 약간 더 효율적일 수 있습니다.
