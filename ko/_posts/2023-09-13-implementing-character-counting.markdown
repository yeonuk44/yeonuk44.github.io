---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_Character_Counting
title: 문자 개수 세기 구현에 대하여(with.Java)
# title: About implementing character counting (with.Java)

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
date: 2023-09-13 09:00:00 +0900
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

### 문자 개수 세기 구현에 대하여(with.Java) 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

알파벳 대소문자로만 이루어진 문자열 my_string이 주어질 때

my_string에서 'A'의 개수, my_string에서 'B'의 개수,..., my_string에서 'Z'의 개수, my_string에서 'a'의 개수, my_string에서 'b'의 개수,...

my_string에서 'z'의 개수를 순서대로 담은 길이 52의 정수 배열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "Programmers"

result: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 2, 0, 1, 0, 0, 3, 1, 0, 0, 0, 0, 0, 0, 0]

my_string에서 'P'가 1개, 'a'가 1개, 'e'가 1개, 'g'가 1개, 'm'이 2개, 'o'가 1개, 'r'가 3개, 's'가 1개 있으므로

[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 2, 0, 1, 0, 0, 3, 1, 0, 0, 0, 0, 0, 0, 0]를 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(String my_string) {
        int[] answer = new int[52];
        for (int i = 0; i < my_string.length(); i++) {
            char c = my_string.charAt(i);

            if (c >= 'A' && c <= 'Z') {
                answer[c - 'A']++;
            } else if (c >= 'a' && c <= 'z') {
                answer[26 + c - 'a']++;
            }
        }

        return answer;
    }
}
```

##### 풀이 설명

이 코드는 주어진 문자열 my_string 내의 알파벳 문자의 출현 빈도를 계산합니다.

결과는 int[] 배열로 반환되며, 이 배열의 각 요소는 특정 알파벳 문자의 출현 횟수를 나타냅니다.

answer 배열은 길이가 52인 정수 배열로, 알파벳의 대문자와 소문자에 대해 각각 카운트를 저장합니다.

인덱스 0부터 25까지는 대문자 'A'부터 'Z'까지의 출현 횟수를 저장합니다.

인덱스 26부터 51까지는 소문자 'a'부터 'z'까지의 출현 횟수를 저장합니다.

**코드의 작동 방식은 다음과 같습니다:**

my_string의 길이만큼 반복하며 각 문자 c를 확인합니다.

만약 c가 대문자라면, 'A'를 빼서 해당 대문자의 위치를 찾고, 그 위치의 카운트를 증가시킵니다. (answer[c - 'A']++)

만약 c가 소문자라면, 'a'를 빼고 26을 더하여 해당 소문자의 위치를 찾고, 그 위치의 카운트를 증가시킵니다. (answer[26 + c - 'a']++)

모든 문자에 대한 처리가 끝나면, answer 배열을 반환합니다. 이 배열은 문자열 내의 각 알파벳 문자의 출현 횟수를 나타냅니다.
