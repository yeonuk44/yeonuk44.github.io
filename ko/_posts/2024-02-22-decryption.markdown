---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Decryption
title: 암호 해독 (with.Java)
# title: Decryption (with.Java)
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
date: 2024-02-22 09:00:00 +0900
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

## "암호 해독" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

군 전략가 머쓱이는 전쟁 중 적군이 다음과 같은 암호 체계를 사용한다는 것을 알아냈습니다.

암호화된 문자열 cipher를 주고받습니다.

그 문자열에서 code의 배수 번째 글자만 진짜 암호입니다.

문자열 cipher와 정수 code가 매개변수로 주어질 때 해독된 암호 문자열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ cipher의 길이 ≤ 1,000
  1 ≤ code ≤ cipher의 길이
  cipher는 소문자와 공백으로만 구성되어 있습니다.
  공백도 하나의 문자로 취급합니다.

#### 입출력 예시

| s             | result |
| ------------- | ------ |
| "1 2 Z 3"     | 4      |
| "10 20 30 40" | 100    |
| "10 Z 20 Z 1" | 1      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int solution(int[] array, int n) {
        int answer = 0;
        int temp = 101;
        Arrays.sort(array);
        for(int i = 0; i < array.length; i++){
            if(temp > Math.abs(n - array[i])){
                answer = array[i];
                temp = Math.abs(n - array[i]);
            }
        }
        return answer;
    }
}
```

### 풀이 설명

- 초기값 설정: temp 변수를 101로 초기화합니다. 이 값은 배열 요소의 최대 차이보다 크게 설정되어 있습니다.
- 배열 정렬: Arrays.sort 메서드를 사용하여 배열을 오름차순으로 정렬합니다.
- 배열 순회: 정렬된 배열을 순회하면서 각 요소와 n의 차이를 계산합니다.
- 가장 가까운 요소 찾기: 현재까지의 최소 차이보다 작은 차이가 나타날 경우, 해당 요소를 answer에 할당하고 temp 값을 갱신합니다.
- 결과 반환: 가장 가까운 요소를 찾았다면 이를 반환합니다.

**코드 장점**

- 오름차순 정렬 활용: 정렬된 배열을 사용하여 n과 가장 가까운 요소를 효율적으로 찾을 수 있습니다.
- 간결한 로직: 간단하면서도 효과적인 로직으로 가장 가까운 배열 요소를 찾고 있습니다.

**코드 단점**

- 고정된 초기값: 초기값 101은 배열 요소의 최대 차이에 따라 결정되어 있습니다. 만약 배열의 값 범위를 벗어나면 이 값을 적절하게 조정해야 합니다.
- 배열이 비어있을 경우 처리 부재: 현재 코드는 배열이 비어있을 때의 처리를 고려하지 않고 있습니다. 빈 배열에 대한 처리를 추가하는 것이 좋습니다.
- 최소 차이가 여러 개인 경우 처리 부재: 현재 코드는 최소 차이가 여러 개인 경우에 대한 처리를 하고 있지 않습니다. 예를 들어, 배열이 [1, 5, 9]이고 n이 6인 경우, 5와 9 모두 최소 차이를 갖습니다. 이에 대한 처리를 추가하는 것이 좋습니다.
