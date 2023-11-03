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

### 배열의 길이에 따라 다른 연산하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr과 정수 n이 매개변수로 주어집니다.

arr의 길이가 홀수라면 arr의 모든 짝수 인덱스 위치에 n을 더한 배열을, arr의 길이가 짝수라면 arr의 모든 홀수 인덱스 위치에 n을 더한 배열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| arr                    | n   | result                 |
| ---------------------- | --- | ---------------------- |
| [49, 12, 100, 276, 33] | 27  | [76, 12, 127, 276, 60] |
| [444, 555, 666, 777]   | 100 | [444, 655, 666, 877]   |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] arr, int n) {
        if(arr.length % 2 != 0){
            for(int i = 0; i < arr.length; i++){
                if(i % 2 == 0){
                    arr[i] += n;
                }
            }
        } else {
            for(int i = 0; i < arr.length; i++){
                if(i % 2 != 0){
                    arr[i] += n;
                }
            }
        }
        return arr;
    }
}
```

##### 풀이 설명

먼저, 배열 arr의 길이가 홀수인지 짝수인지를 확인합니다.

arr.length % 2 != 0 조건으로 길이가 홀수인 경우를 확인하고, 짝수인 경우에는 else 블록을 실행합니다.

길이가 **홀수인** 경우:

for 루프를 사용하여 배열 arr을 순회합니다. i 변수는 배열의 인덱스를 나타냅니다.

if(i % 2 == 0) 조건은 현재 인덱스 i가 짝수 위치인지 확인합니다. 짝수 위치일 경우 해당 원소에 n 값을 더합니다.

길이가 **짝수인** 경우:

이 경우는 else 블록으로 진입하며, 배열 arr을 순회합니다.

if(i % 2 != 0) 조건은 현재 인덱스 i가 홀수 위치인지 확인합니다. 홀수 위치일 경우 해당 원소에 n 값을 더합니다.

변경된 배열 arr을 반환합니다.

이 함수는 주어진 배열 arr의 홀수 또는 짝수 위치의 원소들에 n을 더하는 간단한 연산을 수행합니다.

홀수와 짝수 위치의 원소에 대한 구분은 배열의 길이가 홀수인지 짝수인지를 기준으로 하고, 그에 따라 연산이 수행됩니다.
