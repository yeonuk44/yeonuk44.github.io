---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Power_Of_Two
title: Make the length of an array a power of two (with.Java)
# title: Make the length of an array a power of two (with.Java)
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
date: 2023-10-26 09:00:00 +0900
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

### 빈 배열에 추가, 삭제하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

아무 원소도 들어있지 않은 빈 배열 X가 있습니다.

길이가 같은 정수 배열 arr과 boolean 배열 flag가 매개변수로 주어질 때, flag를 차례대로 순회하며 flag[i]가 true라면 X의 뒤에 arr[i]를 arr[i] × 2 번 추가하고, flag[i]가 false라면 X에서 마지막 arr[i]개의 원소를 제거한 뒤 X를 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| arr             | flag                              | result                   |
| --------------- | --------------------------------- | ------------------------ |
| [3, 2, 4, 1, 3] | [true, false, true, false, false] | [3, 3, 3, 3, 4, 4, 4, 4] |

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr, boolean[] flag) {
        ArrayList<Integer> answer = new ArrayList<>();
        for(int i = 0; i < flag.length; i++){
            if(flag[i]){
                for(int j = 0; j < arr[i] * 2; j++){
                    answer.add(arr[i]);
                }
            } else{
                for(int j = 0; j < arr[i]; j++){
                    answer.remove(answer.size() - 1);
                }
            }
        }
        int[] result = new int[answer.size()];
        for(int i = 0; i < answer.size(); i++){
            result[i] = answer.get(i);
        }
        return result;
    }
}
```

##### 풀이 설명

ArrayList<Integer> answer = new ArrayList<>();: answer라는 정수 배열 리스트를 생성합니다. 이 리스트는 최종 결과를 저장하기 위해 사용됩니다.

for(int i = 0; i < flag.length; i++) : flag 배열의 길이만큼 루프를 시작합니다.

if(flag[i]) : flag[i]가 true인 경우, 다음 작업을 수행합니다. 이 경우는 true인 경우를 처리하는 부분입니다.

for(int j = 0; j < arr[i] _ 2; j++) : arr[i]의 두 배만큼 반복합니다. 이 부분은 현재 arr[i] 값의 두 배만큼 arr[i] 값을 answer 리스트에 추가합니다. 예를 들어, arr[i]가 3이면, 3 _ 2 = 6만큼 3을 answer 리스트에 추가합니다.

else : flag[i]가 false인 경우, 다음 작업을 수행합니다. 이 경우는 false인 경우를 처리하는 부분입니다.

for(int j = 0; j < arr[i]; j++) : arr[i]만큼 반복합니다. 이 부분은 현재 arr[i] 값만큼 answer 리스트에서 요소를 제거합니다. remove 메서드를 사용하여 뒤에서부터 요소를 하나씩 제거합니다.

int[] result = new int[answer.size()];: answer 리스트의 크기에 맞는 int 배열 result를 생성합니다.

for(int i = 0; i < answer.size(); i++) : answer 리스트의 모든 요소를 반복하여 result 배열에 복사합니다.

마지막으로, result 배열을 반환합니다.

이 코드는 flag 배열의 값에 따라 arr 배열의 값을 조작하고, 그 결과를 answer 리스트에 저장한 다음, 최종적으로 result 배열로 변환하여 반환하는 함수입니다.
