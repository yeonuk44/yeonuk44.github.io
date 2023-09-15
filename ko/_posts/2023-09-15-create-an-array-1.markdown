---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Create_An_Array_1
title: 배열 만들기 1(with.Java)
# title: Create an array1 (with.Java)

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
date: 2023-09-15 09:00:00 +0900
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

### 배열 만들기 1(with.Java)

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 n과 k가 주어졌을 때, 1 이상 n이하의 정수 중에서 k의 배수를 오름차순으로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| n   | k   | result      |
| --- | --- | ----------- |
| 10  | 3   | [3, 6, 9]   |
| 15  | 5   | [5, 10, 15] |

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int n, int k) {
        int[] answer = new int[n/k];
        int j = 0;
        for(int i = 1; i <= n; i++){
            if(i % k == 0) answer[j++] = i;
        }
        return answer;
    }
}
```

##### 풀이 설명

int[] answer = new int[n/k];: n/k 길이의 정수 배열 answer를 생성합니다. 이 배열은 k의 배수인 숫자를 저장하기 위해 사용됩니다.

int j = 0;: 배열 answer에 숫자를 저장하기 위한 인덱스 변수 j를 초기화합니다.

for(int i = 1; i <= n; i++) {: 1부터 n까지의 숫자를 반복하면서 검사합니다.

if(i % k == 0) answer[j++] = i;: 현재 숫자 i가 k의 배수인지 확인합니다. 만약 i가 k의 배수라면, 그 값을 배열 answer에 저장하고 j를 증가시켜 다음 인덱스에 저장할 준비를 합니다.

return answer;: 최종적으로 k의 배수인 숫자가 저장된 배열 answer를 반환합니다.

이 코드는 주어진 범위 내에서 k의 배수를 찾아서 배열에 저장하는 간단한 작업을 수행합니다. 반환되는 배열에는 k의 배수가 오름차순으로 저장되어 있습니다.
