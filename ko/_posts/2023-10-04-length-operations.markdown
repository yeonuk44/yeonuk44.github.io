---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Length_Operations
title: 길이에 따른 연산(with.Java)
# title: Length-based operations (with.Java)

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
date: 2023-10-04 09:00:00 +0900
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

### 길이에 따른 연산(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수가 담긴 리스트 num_list가 주어질 때, 리스트의 길이가 11 이상이면 리스트에 있는 모든 원소의 합을 10 이하이면 모든 원소의 곱을 return하도록 solution 함수를 완성해주세요.

##### 입출력 예시

| num_list                                | result |
| --------------------------------------- | ------ |
| [3, 4, 5, 2, 5, 4, 6, 7, 3, 7, 2, 2, 1] | 51     |
| [2, 3, 4, 5]                            | 120    |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 1;
        if(num_list.length > 10){
            for(int i = 0; i < num_list.length; i++){
                answer += num_list[i];
            }
            answer = answer - 1;
        }else {
            for(int i = 0; i < num_list.length; i++){
                answer = answer * num_list[i];
            }
        }
        return answer;
    }
}
```

##### 풀이 설명

int answer = 1;: 결과를 저장할 변수 answer를 초기화합니다. 초기값은 1입니다.

if(num_list.length > 10): 입력 배열 num_list의 길이가 10보다 큰 경우:

배열의 모든 요소를 더한 값을 answer에 더합니다.

마지막에 1을 빼서 결과를 계산합니다.

else: 그 외의 경우 (배열의 길이가 10 이하인 경우):

배열의 모든 요소를 곱한 값을 answer에 저장합니다.

return answer;: 계산된 결과를 반환합니다.
