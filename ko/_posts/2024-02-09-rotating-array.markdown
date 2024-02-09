---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Rotating_Array
title: 배열 회전시키기 (with.Java)
# title: Rotating an array (with.Java)
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
date: 2024-02-09 09:00:00 +0900
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

## "공 던지기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 친구들과 동그랗게 서서 공 던지기 게임을 하고 있습니다.

공은 1번부터 던지며 오른쪽으로 한 명을 건너뛰고 그다음 사람에게만 던질 수 있습니다.

친구들의 번호가 들어있는 정수 배열 numbers와 정수 K가 주어질 때, k번째로 공을 던지는 사람의 번호는 무엇인지 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 2 < numbers의 길이 < 100
- 0 < k < 1,000
- numbers의 첫 번째와 마지막 번호는 실제로 바로 옆에 있습니다.
- numbers는 1부터 시작하며 번호는 순서대로 올라갑니다.

#### 입출력 예시

| numbers            | k   | result |
| ------------------ | --- | ------ |
| [1, 2, 3, 4]       | 2   | 3      |
| [1, 2, 3, 4, 5, 6] | 5   | 3      |
| [1, 2, 3]          | 3   | 2      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] numbers, int k) {
        int answer = 0;
        answer = numbers[2 * (k -1) % numbers.length];
        return answer;
    }
}
```

### 풀이 설명

여기서 numbers.length는 배열 numbers의 길이를 나타냅니다.

주어진 문제에서는 오른쪽으로 한 명을 건너뛰며 공을 던지는데, 이를 구현하기 위해 (k - 1)에 2를 곱하고 numbers.length로 나눈 나머지를 사용합니다.

이렇게 함으로써 오른쪽으로 한 명을 건너뛰어 k번째로 공을 던지는 사람의 번호를 찾을 수 있습니다.

예를 들어, 배열 numbers가 [1, 2, 3, 4, 5]이고, k가 3인 경우를 생각해봅시다.

- 처음에는 1이 공을 던집니다. (0번째 머쓱이)
- 다음으로 3이 공을 던집니다. (2번째 머쓱이)
- 그리고 5가 공을 던집니다. (4번째 머쓱이)
  이를 표현한 코드가 numbers[2 * (k - 1) % numbers.length]입니다.

나머지 연산자를 사용함으로써 배열을 순환하면서 k번째로 공을 던지는 머쓱이의 번호를 찾을 수 있습니다.

**추가**
나머지 연산자를 사용하면 배열을 순환하는 효과를 얻을 수 있습니다.

배열의 길이를 n이라고 할 때, 인덱스 i에 대해 i % n은 배열을 순환하면서 반복됩니다.

이를 이용하여 배열에서 특정 위치의 값을 가져올 때, 배열의 길이로 나눈 나머지를 사용하면 편리하게 순환 동작을 구현할 수 있습니다.

예를 들어, 배열의 길이가 5인 경우:

- 0 % 5는 0
- 1 % 5는 1
- 2 % 5는 2
- 3 % 5는 3
- 4 % 5는 4
- 5 % 5는 다시 0
- 6 % 5는 1

이런 식으로 나머지 연산을 통해 배열의 인덱스를 계산하면, 배열이 순환하는 효과를 얻을 수 있습니다.

이를 통해 주기적으로 반복되는 배열 요소에 쉽게 접근할 수 있게 됩니다.
