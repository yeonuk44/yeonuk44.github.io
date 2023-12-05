---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Converting_A_Sequence_To_Meet_A_Condition_3
title: 조건에 맞게 수열 변환하기 3(with.Java)
# title: Converting a sequence to meet a condition 3 (with.Java)
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
date: 2023-12-04 09:00:00 +0900
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

## "조건에 맞게 수열 변환하기 3" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 배열 arr와 자연수 k가 주어집니다.

만약 k가 홀수라면 arr의 모든 원소에 k를 곱하고, k가 짝수라면 arr의 모든 원소에 k를 더합니다.

이러한 변환을 마친 후의 arr를 return 하는 solution 함수를 완성해 주세요.

#### 입출력 예시

| arr                    | k   | result                   |
| ---------------------- | --- | ------------------------ |
| [1, 2, 3, 100, 99, 98] | 3   | [3, 6, 9, 300, 297, 294] |
| [1, 2, 3, 100, 99, 98] | 2   | [3, 4, 5, 102, 101, 100] |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] arr, int k) {
        if(k % 2 == 0){
            for(int i = 0; i < arr.length; i++){
                arr[i] += k;
            }
        }else{
            for(int i = 0; i < arr.length; i++){
                arr[i] = arr[i] * k;
            }
        }
        return arr;
    }
}
```

#### 풀이 설명

if(k % 2 == 0) : 만약 k가 짝수인 경우:

배열 arr의 각 요소에 k를 더합니다.

else : 그 외의 경우 (즉, k가 홀수인 경우):

배열 arr의 각 요소를 k와 곱합니다.

return arr;: 변경된 배열 arr을 반환합니다.

이 코드는 k의 홀짝 여부에 따라 배열의 요소를 다르게 변환합니다.

k가 짝수이면 각 요소에 k를 더하고, k가 홀수이면 각 요소를 k와 곱하여 반환합니다.
