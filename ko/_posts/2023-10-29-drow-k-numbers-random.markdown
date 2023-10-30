---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Draw_K_Numbers_Random
title: 무작위로 K개의 수 뽑기(with.Java)
# title: Draw K numbers at random (with.Java)
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
date: 2023-10-29 09:00:00 +0900
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

### 무작위로 K개의 수 뽑기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

랜덤으로 서로 다른 k개의 수를 저장한 배열을 만드려고 합니다. 적절한 방법이 떠오르지 않기 때문에 일정한 범위 내에서 무작위로 수를 뽑은 후, 지금까지 나온적이 없는 수이면 배열 맨 뒤에 추가하는 방식으로 만들기로 합니다.

이미 어떤 수가 무작위로 주어질지 알고 있다고 가정하고, 실제 만들어질 길이 k의 배열을 예상해봅시다.

정수 배열 arr가 주어집니다. 문제에서의 무작위의 수는 arr에 저장된 순서대로 주어질 예정이라고 했을 때, 완성될 배열을 return 하는 solution 함수를 완성해 주세요.

단, 완성될 배열의 길이가 k보다 작으면 나머지 값을 전부 -1로 채워서 return 합니다.

##### 입출력 예시

| arr                | k   | result         |
| ------------------ | --- | -------------- |
| [0, 1, 1, 2, 2, 3] | 3   | [0, 1, 2]      |
| [0, 1, 1, 1, 1]    | 4   | [0, 1, -1, -1] |

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr, int k) {
        ArrayList<Integer> list = new ArrayList<>();
        int[] answer = new int[k];
        for(int i = 0; i < arr.length; i++){
            if(!list.contains(arr[i])){
                list.add(arr[i]);
            }
            if(list.size() == k){
                break;
            }
        }
        while (list.size() < k) {
            list.add(-1);
        }
        for(int i = 0; i < k; i++){
            answer[i] = list.get(i);
        }
        return answer;
    }
}
```

##### 풀이 설명

ArrayList<Integer> list = new ArrayList<>();: Integer 타입의 요소를 저장하는 ArrayList를 생성합니다. 이 리스트는 중복을 제거하고 결과를 저장하는데 사용됩니다.

int[] answer = new int[k];: 결과를 저장할 배열 answer를 생성합니다. k의 크기로 초기화됩니다.

for(int i = 0; i < arr.length; i++): 입력 배열 arr을 반복하면서 중복을 제거하여 list에 추가하는 반복문을 시작합니다.

if(!list.contains(arr[i])): list에 arr[i]가 포함되어 있지 않다면 (즉, 중복되지 않는 경우),

list.add(arr[i]);: list에 arr[i]를 추가합니다.

if(list.size() == k): list의 크기가 k와 같아지면 반복문을 종료합니다. 즉, 원하는 결과 크기에 도달하면 더 이상 중복을 제거하지 않습니다.

while (list.size() < k): list의 크기가 k보다 작은 경우,

list.add(-1);: -1을 list에 추가하여 k의 크기에 도달하도록 합니다.

for(int i = 0; i < k; i++): list의 요소를 배열 answer에 복사하는 반복문을 시작합니다.

answer[i] = list.get(i);: list의 i번째 요소를 answer의 i번째 위치에 복사합니다.

return answer;: 최종 결과인 answer 배열을 반환합니다.

이 코드는 중복된 값을 제거하고, 필요에 따라 -1을 채워서 결과 배열을 만들어 반환합니다. 결과 배열의 크기는 k와 같거나 미만이며, 중복된 값은 하나만 포함됩니다.
