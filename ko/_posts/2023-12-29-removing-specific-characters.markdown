---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Removing_Specific_Characters
title: 특정 문자 제거하기(with.Java)
# title: Removing Specific Characters (with.Java)
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
date: 2023-12-29 09:00:00 +0900
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

## "짝수는 싫어요" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 n이 매개변수로 주어질 때, n 이하의 홀수가 오름차순으로 담긴 배열을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예시

| n   | result                      |
| --- | --------------------------- |
| 10  | [1, 3, 5, 7, 9]             |
| 15  | [1, 3, 5, 7, 9, 11, 13, 15] |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int n) {
        int[] answer;
        if(n % 2 == 0){
            answer = new int[n / 2];
        } else {
            answer = new int[n / 2 + 1];
        }

        int count = 0;
        for(int i = 1; i <= n; i++){
            if(i % 2 != 0){
                answer[count++] = i;
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

public int[] solution(int n) : 함수 solution을 선언하고, 양수 정수 n을 입력 매개변수로 받습니다. 이 함수는 정수 배열을 반환합니다.

int[] answer;: 정수 배열 answer를 선언합니다. 이 배열은 나중에 홀수를 저장할 배열로 사용될 것입니다.

if (n % 2 == 0) : 입력된 n이 짝수인 경우, 홀수의 개수가 (n / 2)개가 될 것이므로 answer 배열의 크기를 (n / 2)로 초기화합니다.

answer = new int[n / 2];: 짝수일 때 배열 크기를 (n / 2)로 초기화합니다.

else : 입력된 n이 홀수인 경우, 홀수의 개수가 ((n / 2) + 1)개가 될 것이므로 answer 배열의 크기를 ((n / 2) + 1)로 초기화합니다.

answer = new int[n / 2 + 1];: 홀수일 때 배열 크기를 ((n / 2) + 1)로 초기화합니다.

int count = 0;: count 변수를 선언하고 0으로 초기화합니다. 이 변수는 홀수를 answer 배열에 저장할 때 사용됩니다.

for (int i = 1; i <= n; i++) : 1부터 n까지의 모든 정수에 대해 반복합니다.

if (i % 2 != 0) : 현재 숫자 i가 홀수인 경우, 즉 2로 나누었을 때 나머지가 1인 경우, 아래의 작업을 수행합니다.

answer[count++] = i;: 현재 홀수 숫자 i를 answer 배열에 저장하고, count 변수를 증가시켜 다음 홀수를 저장할 위치를 나타냅니다.

return answer;: 홀수로 채워진 answer 배열을 함수의 반환 값으로 반환합니다.
