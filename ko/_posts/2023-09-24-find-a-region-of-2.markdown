---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_A_Region_Of_2
title: 2의 영역을 찾는 방법에 대하여(with.Java)
# title: How to find a region of 2 (with.Java)

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
date: 2023-09-24 09:00:00 +0900
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

### 2의 영역을 찾는 방법에 대하여(with.Java) 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr가 주어집니다. 배열 안의 2가 모두 포함된 가장 작은 연속된 부분 배열을 return 하는 solution 함수를 완성해 주세요.

단, arr에 2가 없는 경우 [-1]을 return 합니다.

##### 입출력 예시

arr: [1, 2, 1, 4, 5, 2, 9]

result: [2, 1, 4, 5, 2]

2가 있는 인덱스는 1번, 5번 인덱스뿐이므로 1번부터 5번 인덱스까지의 부분 배열인 [2, 1, 4, 5, 2]를 return 합니다.

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int[] solution(int[] arr) {
        int startIndex = -1;
        int endIndex = -1;

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == 2) {
                if (startIndex == -1) {
                    startIndex = i;
                }
                endIndex = i;
            }
        }

        if (startIndex == -1 || endIndex == -1) {
            return new int[]{-1};
        }

        int[] answer = new int[endIndex - startIndex + 1];
        for (int j = 0; j < answer.length; j++) {
            answer[j] = arr[startIndex + j];
        }

        return answer;
    }
}
```

##### 풀이 설명

변수 초기화: startIndex와 endIndex는 각각 -1로 초기화됩니다. 이러한 값은 '2'가 아직 발견되지 않았음을 나타냅니다.

'2'의 위치 찾기: 주어진 배열 arr을 순회하면서 '2'가 있는 위치를 찾습니다.

startIndex는 처음으로 발견된 '2'의 인덱스를 저장합니다.

endIndex는 마지막으로 발견된 '2'의 인덱스를 저장합니다.

즉, 반복문이 끝나면 startIndex와 endIndex는 배열 내 첫 번째 '2'와 마지막 '2'의 위치를 나타냅니다.

'2'가 없는 경우의 처리: startIndex나 endIndex가 -1인 경우, '2'가 없는 것으로 판단하고 [-1]을 반환합니다.

부분 배열 생성: startIndex와 endIndex 사이의 부분 배열을 생성합니다.

answer 배열의 길이는 (endIndex - startIndex + 1)이며, 이를 통해 startIndex에서 endIndex까지의 원소를 포함하게 됩니다.

부분 배열의 각 원소는 원본 배열의 startIndex에서 시작하여 endIndex까지의 값을 복사합니다.

결과 반환: 만들어진 부분 배열 answer를 반환합니다. 이 배열은 arr에서 첫 번째 '2'와 마지막 '2' 사이의 모든 원소를 포함하고 있습니다.
