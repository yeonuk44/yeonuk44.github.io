---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Different_Length_Of_Array
title: 배열의 길이에 따라 다른 연산하기(with.Java)
# title: Performing different operations on the length of an array (with.Java)
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
date: 2023-11-02 09:00:00 +0900
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

### 배열 비교하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

이 문제에서 두 정수 배열의 대소관계를 다음과 같이 정의합니다.

두 배열의 길이가 다르다면, 배열의 길이가 긴 쪽이 더 큽니다.

배열의 길이가 같다면 각 배열에 있는 모든 원소의 합을 비교하여 다르다면 더 큰 쪽이 크고, 같다면 같습니다.

두 정수 배열 arr1과 arr2가 주어질 때, 위에서 정의한 배열의 대소관계에 대하여 arr2가 크다면 -1, arr1이 크다면 1, 두 배열이 같다면 0을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| arr1             | arr2             | result |
| ---------------- | ---------------- | ------ |
| [49, 13]         | [70, 11, 2]      | -1     |
| [100, 17, 84, 1] | [55, 12, 65, 36] | 1      |
| [1, 2, 3, 4, 5]  | [3, 3, 3, 3, 3]  | 0      |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] arr) {
        int[] answer;
        int idx = 1;
        for(int i = 0; i < (int) Math.pow(2,10); i++){
            if(arr.length == (int) Math.pow(2,i)){
                idx = (int) Math.pow(2,i);
                break;
            } else{
                if(arr.length < (int) Math.pow(2,i)){
                    idx = (int) Math.pow(2,i);
                    break;
                }
            }
        }
        answer = new int[idx];
        for(int i = 0; i < answer.length; i++){
            if(arr.length - 1 < i){
                answer[i] = 0;
            }else{
                answer[i] = arr[i];
            }
        }
        return answer;
    }
}
```

##### 풀이 설명

먼저, 두 배열 arr1과 arr2의 길이를 비교합니다. 길이가 같을 때와 길이가 다를 때로 나뉩니다.

만약 두 배열의 길이가 같다면, 두 배열을 돌며 각 배열의 모든 요소를 합산합니다.

compare1 변수에는 arr1의 모든 요소의 합을 저장하고, compare2 변수에는 arr2의 모든 요소의 합을 저장합니다.

이제 compare1과 compare2를 비교하여 두 합의 크기를 비교합니다.

만약 compare1이 compare2보다 크면, answer에 1을 저장합니다.

만약 compare1이 compare2보다 작으면, answer에 -1을 저장합니다.

두 합이 같다면, answer에 0을 저장합니다.

만약 두 배열의 길이가 다르다면, 길이가 더 긴 배열을 찾아내어 answer에 1 또는 -1을 저장합니다.

코드는 주어진 두 배열을 비교하고, 두 배열의 길이와 합을 고려하여 결과를 반환하는 간단한 함수입니다. 결과 값은 answer에 저장되며, 1, -1, 또는 0 중 하나가 됩니다.
