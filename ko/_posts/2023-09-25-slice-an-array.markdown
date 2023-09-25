---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Slice_An_Array
title: 배열 조각하기, 주어진 arr를 query값을 통해 인덱스 홀짝을 판별하고 제어하는 방법에 대하여 (with.Java)
# title: Slice an Array (with.Java)

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
date: 2023-09-25 09:00:00 +0900
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

### 배열 조각하기, 주어진 arr를 query값을 통해 인덱스 홀짝을 판별하고 제어하는 방법에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr와 query가 주어집니다.

query를 순회하면서 다음 작업을 반복합니다.

짝수 인덱스에서는 arr에서 query[i]번 인덱스를 제외하고 배열의 query[i]번 인덱스 뒷부분을 잘라서 버립니다.

홀수 인덱스에서는 arr에서 query[i]번 인덱스는 제외하고 배열의 query[i]번 인덱스 앞부분을 잘라서 버립니다.

위 작업을 마친 후 남은 arr의 부분 배열을 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

arr: [0, 1, 2, 3, 4, 5]

query: [4,1,2]

result: [1, 2, 3]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr, int[] query) {
        for(int i = 0; i < query.length; i++) {
            if(i % 2 == 0) {
                arr = Arrays.copyOfRange(arr, 0, query[i] + 1);
            } else {
                arr = Arrays.copyOfRange(arr, query[i], arr.length);
            }
        }
        return arr;
    }
}
```

##### 풀이 설명

solution 함수는 두 개의 정수 배열 arr과 query를 입력 받습니다. arr는 조작할 대상 배열이며, query는 조작을 수행할 인덱스 정보를 담고 있습니다.

함수의 시작 부분에서 query의 길이만큼 루프를 돌면서 다음과 같은 작업을 수행합니다:

짝수 인덱스의 경우: 루프 변수 i가 짝수일 때는 query[i]번째 인덱스를 포함하여 이후의 모든 요소를 arr에서 제거합니다. 예를 들어 arr = [0, 1, 2, 3, 4, 5]이고 query[i]가 2라면, 결과는 [0, 1, 2]가 됩니다.

홀수 인덱스의 경우: i가 홀수일 때는 query[i]번째 인덱스부터 arr의 끝까지 남기고, 그 앞의 모든 요소를 제거합니다. 예를 들어 arr = [0, 1, 2, 3, 4, 5]이고 query[i]가 2라면, 결과는 [2, 3, 4, 5]가 됩니다.

이렇게 query의 모든 요소에 대해 위 작업을 수행하면, 최종적으로 남은 arr의 부분 배열이 반환됩니다.

자바의 Arrays.copyOfRange 메서드를 사용하면 배열의 특정 범위를 쉽게 복사할 수 있어, 위 작업을 효율적으로 수행할 수 있습니다.

###### 참고

arr의 배열의 크기는 정해져 있는데 Arrays.copyOfRange를 쓰면 요소가 줄어듭니다. **배열의 크기도 함께 줄어들까요?**

네, 맞습니다! Arrays.copyOfRange 메서드는 원본 배열에서 지정된 범위의 요소를 추출하여 새로운 배열을 생성합니다. 따라서 생성된 새로운 배열의 크기는 지정된 범위의 길이와 일치하게 됩니다.

예를 들어, Arrays.copyOfRange(arr, 0, 3)를 호출하면 원본 배열 arr의 0번 인덱스부터 2번 인덱스까지의 요소를 복사하여 새로운 배열을 생성합니다. 따라서 새로운 배열의 크기는 3이 됩니다.

이렇게 Arrays.copyOfRange를 사용하면 원하는 범위의 요소를 쉽게 추출하고, 해당 범위에 맞는 크기의 새로운 배열을 생성할 수 있습니다. 따라서 본 문제에서 arr의 크기는 query의 요소에 따라 계속 변동하게 됩니다.

수고하셨습니다.
