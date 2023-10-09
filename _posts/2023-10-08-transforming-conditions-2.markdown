---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Transforming_conditions_2
title: Transforming a sequence based on conditions 2 (with.Java)
# title: Transforming a sequence based on conditions 2 (with.Java)

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
date: 2023-10-08 09:00:00 +0900
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

### 조건에 맞게 수열 변환하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr가 주어집니다.

arr의 각 원소에 대해 값이 50보다 크거나 같은 짝수라면 2로 나누고, 50보다 작은 홀수라면 2를 곱합니다.

그 결과인 정수 배열을 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| arr                    | result                |
| ---------------------- | --------------------- |
| [1, 2, 3, 100, 99, 98] | [2, 2, 6, 50, 99, 49] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int[] arr) {
        int[] answer = new int[arr.length];
        for(int i = 0; i < arr.length; i++){
            if(arr[i] >= 50 && arr[i] % 2 == 0){
                answer[i] = arr[i] / 2;
            }else if(arr[i] < 50 && arr[i] % 2 != 0){
                answer[i] = arr[i] * 2;
            }else{
                answer[i] = arr[i];
            }
        }
        return answer;
    }
}
```

##### 풀이 설명

int[] answer = new int[arr.length];: 결과를 저장할 배열 answer를 입력 배열 arr과 동일한 길이로 생성합니다.

for(int i = 0; i < arr.length; i++) : 입력 배열 arr를 반복하면서 각 요소를 검사합니다.

if(arr[i] >= 50 && arr[i] % 2 == 0) : 현재 요소가 50 이상이면서 짝수인 경우:

현재 요소를 2로 나눈 값을 answer 배열에 저장합니다.

else if(arr[i] < 50 && arr[i] % 2 != 0) : 현재 요소가 50 미만이면서 홀수인 경우:

현재 요소를 2배로 곱한 값을 answer 배열에 저장합니다.

else : 위의 두 조건을 만족하지 않는 경우 (즉, 50 이상이면서 짝수가 아니거나, 50 미만이면서 홀수가 아닌 경우):

현재 요소를 그대로 answer 배열에 저장합니다.

return answer;: 최종적으로 연산이 완료된 answer 배열을 반환합니다.
