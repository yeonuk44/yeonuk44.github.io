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

### 배열 만들기 6에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

0과 1로만 이루어진 정수 배열 arr가 주어집니다. arr를 이용해 새로운 배열 stk을 만드려고 합니다.

i의 초기값을 0으로 설정하고 i가 arr의 길이보다 작으면 다음을 반복합니다.

만약 stk이 빈 배열이라면 arr[i]를 stk에 추가하고 i에 1을 더합니다.

stk에 원소가 있고, stk의 마지막 원소가 arr[i]와 같으면 stk의 마지막 원소를 stk에서 제거하고 i에 1을 더합니다.

stk에 원소가 있는데 stk의 마지막 원소가 arr[i]와 다르면 stk의 맨 마지막에 arr[i]를 추가하고 i에 1을 더합니다.

위 작업을 마친 후 만들어진 stk을 return 하는 solution 함수를 완성해 주세요.

단, 만약 빈 배열을 return 해야한다면 [-1]을 return 합니다.

##### 입출력 예시

| arr             | result          |
| --------------- | --------------- |
| [0, 1, 1, 1, 0] | [0, 1, 0]       |
| [0, 1, 0, 1, 0] | [0, 1, 0, 1, 0] |
| [0, 1, 1, 0]    | [-1]            |

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr) {
        int[] answer;
        ArrayList<Integer> stk = new ArrayList<>();
        for(int i = 0; i < arr.length; i++){
            if(stk.isEmpty()){
                stk.add(arr[i]);
            } else if(stk.get(stk.size() - 1) != arr[i]){
                stk.add(arr[i]);
            } else {
                stk.remove(stk.size() - 1);
            }
        }
        if(stk.isEmpty()){
            answer = new int[1];
            answer[0] = -1;
        }else {
            answer = new int[stk.size()];
            for(int i = 0; i < stk.size(); i++){
                answer[i] = stk.get(i);
            }
        }

        return answer;
    }
}
```

##### 풀이 설명

int[] answer;: 결과 배열을 선언합니다.

ArrayList<Integer> stk = new ArrayList<>();: stk라는 이름의 정수형 ArrayList를 생성합니다. 이 ArrayList는 중복된 요소를 제거하기 위한 임시 저장소 역할을 합니다.

for(int i = 0; i < arr.length; i++): 주어진 배열 arr을 순회합니다.

if(stk.isEmpty()): stk가 비어있는 경우, 현재 배열 요소를 추가합니다.

stk.add(arr[i]);: stk에 현재 배열 요소 arr[i]를 추가합니다.
else if(stk.get(stk.size() - 1) != arr[i]): stk가 비어있지 않고, 현재 배열 요소가 stk의 마지막 요소와 다를 경우, 현재 배열 요소를 추가합니다. 이는 중복을 제거하기 위한 조건입니다.

stk.add(arr[i]);: stk에 현재 배열 요소 arr[i]를 추가합니다.
else: stk가 비어있지 않고, 현재 배열 요소가 stk의 마지막 요소와 동일한 경우, 중복된 요소이므로 stk의 마지막 요소를 제거합니다.

stk.remove(stk.size() - 1);: stk의 마지막 요소를 제거합니다.
if(stk.isEmpty()): stk가 비어있으면 중복된 요소가 없는 것으로 처리됩니다.

answer = new int[1];: 결과 배열을 크기 1로 초기화합니다.

answer[0] = -1;: 결과 배열의 유일한 요소를 -1로 설정합니다.

그렇지 않은 경우, stk에 남아있는 요소가 중복되지 않은 요소입니다. 이를 answer 배열로 복사합니다.

answer = new int[stk.size()];: 결과 배열을 stk의 크기와 동일한 크기로 초기화합니다.

배열 복사를 위해 루프를 사용하여 stk의 요소를 answer로 복사합니다.

최종적으로 answer 배열을 반환합니다.
