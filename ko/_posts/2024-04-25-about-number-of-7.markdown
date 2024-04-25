---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Of_7
title: 7의 개수(with.Java)
# title: Number of 7 (with.Java)
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
date: 2024-04-25 09:00:00 +0900
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

## "잘라서 배열로 저장하기(with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 my_str과 n이 매개변수로 주어질 때, my_str을 길이 n씩 잘라서 저장한 배열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ my_str의 길이 ≤ 100
- 1 ≤ n ≤ my_str의 길이
- my_str은 알파벳 소문자, 대문자, 숫자로 이루어져 있습니다.

#### 입출력 예시

| my_str             | n   | result                       |
| ------------------ | --- | ---------------------------- |
| "abc1Addfggg4556b" | 6   | ["abc1Ad", "dfggg4", "556b"] |
| "abcdef123"        | 3   | ["abc", "def", "123"]        |

<!-- | my_string | result   |
| --------- | -------- |
| "Bcad"    | "abcd"   |
| "heLLo"   | "ehllo"  |
| "Python"  | "hnopty" | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public String[] solution(String my_str, int n) {
        int length = my_str.length();
        int arrayLength = (int) Math.ceil((double) length / n);

        String[] answer = new String[arrayLength];

        for (int i = 0; i < arrayLength; i++) {
            int start = i * n;
            int end = Math.min(start + n, length);
            answer[i] = my_str.substring(start, end);
        }

        return answer;
    }
}
```

### 풀이 설명

- 문자열 길이 계산: 주어진 문자열의 길이를 계산하여 length 변수에 저장합니다.
- 나눌 배열의 길이 계산: 문자열을 나눌 배열의 길이를 계산하기 위해 문자열 길이를 주어진 길이로 나눈 뒤, 올림 연산을 수행하여 나머지가 발생하면 하나의 배열을 추가합니다. 이 값을 arrayLength 변수에 저장합니다.
- 결과를 저장할 배열 생성: arrayLength 길이의 문자열 배열을 생성하여 answer 변수에 저장합니다.
- 문자열을 일정 길이로 나누어 배열에 저장: for 루프를 통해 문자열을 일정 길이로 나누고, 각 부분 문자열을 answer 배열에 저장합니다. 시작 인덱스는 `i * n`으로 계산하고, 종료 인덱스는 start + n이지만, 만약 마지막 부분이라면 문자열 길이보다 클 수 없으므로 Math.min을 사용하여 두 값 중 작은 값을 선택합니다.
- 결과 배열 반환: 나누어진 부분 문자열이 저장된 answer 배열을 반환합니다.

**코드 장점**

- 일정 길이로 문자열을 나누는 유연성: 주어진 문자열을 원하는 길이로 나누어 배열에 저장할 수 있는 일반적인 방법을 제공합니다.
- 문자열의 길이에 따라 배열의 크기를 동적으로 조정: 입력 문자열의 길이에 따라 배열의 크기를 동적으로 조정하여 메모리를 효율적으로 사용합니다.

**코드 단점**

- 문자열 길이에 따라 배열 크기가 달라질 수 있음: 문자열의 길이와 주어진 길이에 따라 배열의 크기가 달라지므로, 예상치 못한 메모리 사용량을 초래할 수 있습니다.
- 나누어진 부분 문자열의 배열에 대한 불변성: 한 번 나누어진 부분 문자열이 저장된 배열은 변경할 수 없으며, 나중에 해당 부분 문자열을 수정할 수 없습니다.
