---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Power_Of_Two
title: 배열의 길이를 2의 거듭제곱으로 만들기(with.Java)
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

### 배열의 길이를 2의 거듭제곱으로 만들기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr이 매개변수로 주어집니다.

arr의 길이가 2의 정수 거듭제곱이 되도록 arr 뒤에 정수 0을 추가하려고 합니다.

arr에 최소한의 개수로 0을 추가한 배열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| arr                | result                   |
| ------------------ | ------------------------ |
| [1, 2, 3, 4, 5, 6] | [1, 2, 3, 4, 5, 6, 0, 0] |
| [58, 172, 746, 89] | [58, 172, 746, 89]       |

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

int idx = 1;: idx라는 정수 변수를 선언하고 초기값을 1로 설정합니다. 이 변수는 새로운 배열의 크기를 결정하는 데 사용됩니다.

for (int i = 0; i < (int) Math.pow(2, 10); i++) {: 0부터 2^10 (1024)까지의 값을 순차적으로 검사하는 for 루프를 시작합니다. 이 루프는 i를 증가시키면서 arr의 길이와 비교하여 적절한 배열 크기를 찾습니다.

if (arr.length == (int) Math.pow(2, i)) {: 현재 i값으로 계산한 2의 거듭제곱이 arr의 길이와 일치하면 적절한 배열 크기를 찾은 것이므로 idx를 해당 크기로 설정하고 루프를 종료합니다.

else { if (arr.length < (int) Math.pow(2, i)) { idx = (int) Math.pow(2, i); break; } }: arr의 길이가 현재 i로 계산한 2의 거듭제곱보다 작으면 idx를 해당 크기로 설정하고 루프를 종료합니다.

answer = new int[idx];: idx 크기로 새로운 배열 answer를 생성합니다.

배열 arr의 내용을 새로운 배열 answer로 복사하되, arr의 길이를 초과하는 부분은 0으로 초기화합니다.

answer 배열을 반환합니다.

위의 코드처럼도 문제를 풀었지만 반복문을 너무 많이 사용하는 느낌이 있습니다. 코드를 더 간결하게 만들어보겠습니다.

###### 개선된 코드

```java
class Solution {
    public int[] solution(int[] arr) {
        int idx = 1;
        while (idx < arr.length) {
            idx *= 2;
        }

        int[] answer = new int[idx];
        for (int i = 0; i < arr.length; i++) {
            answer[i] = arr[i];
        }
        return answer;
    }
}
```

###### 개선된 코드 해설

첫 번째 코드 (Math.pow 사용):

이 코드에서는 for 루프를 사용하여 2의 거듭제곱을 계산하고, 이 값과 arr의 길이를 비교하여 적절한 배열 크기를 찾습니다. 루프가 실행될 때마다 Math.pow 함수를 호출하여 2의 거듭제곱 값을 계산합니다.
두 번째 코드 (단순 while 루프 사용):

두 번째 코드에서는 while 루프를 사용하여 간단하게 2의 거듭제곱 값을 계산합니다. idx 변수는 초기값 1에서 시작하여 arr의 길이보다 작을 때까지 2를 곱하며 계산합니다.
두 코드는 기능적으로는 동일한 결과를 제공하지만, 두 번째 코드가 더 간결하고 효율적입니다. Math.pow 함수 호출 없이 while 루프를 사용하여 배열 크기를 결정하므로 코드가 간단해집니다. 또한 while 루프를 사용하면 특정 배열 크기까지 2를 반복적으로 곱하는 방식으로 크기를 찾아내므로 더 효율적인 방법입니다.

따라서 두 번째 코드가 더 선호되는 방식이며, 같은 결과를 더 효율적으로 얻을 수 있습니다.
