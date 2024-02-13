---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Factorial
title: 팩토리얼 (with.Java)
# title: Factorial (with.Java)
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
date: 2024-02-13 09:00:00 +0900
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

## "문자열 정렬하기 1" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 my_string이 매개변수로 주어질 때, my_string 안에 있는 숫자만 골라 오름차순 정렬한 리스트를 return 하도록 solution 함수를 작성해보세요.

#### 제한사항

- 1 ≤ my_string의 길이 ≤ 100
- my_string에는 숫자가 한 개 이상 포함되어 있습니다.
- my_string은 영어 소문자 또는 0부터 9까지의 숫자로 이루어져 있습니다.

#### 입출력 예시

| my_string   | result          |
| ----------- | --------------- |
| "hi12392"   | [1, 2, 2, 3, 9] |
| "p2o4i8gj2" | [2, 2, 4, 8]    |
| "abcde0"    | [0]             |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int[] solution(String my_string) {
        List<Integer> numbers = new ArrayList<>();

        for (char ch : my_string.toCharArray()) {
            if (Character.isDigit(ch)) {
                numbers.add(Character.getNumericValue(ch));
            }
        }

        Collections.sort(numbers);
        int[] answer = numbers.stream().mapToInt(i -> i).toArray();

        return answer;
    }
}
```

### 풀이 설명

solution(String my_string): 주어진 문자열 my_string에서 숫자를 추출하여 정렬된 배열로 반환한다.

List<Integer> numbers: 숫자를 저장할 리스트.

문자열을 순회하면서 Character.isDigit(ch)를 사용하여 각 문자가 숫자인지 확인하고, 숫자라면 Character.getNumericValue(ch)를 사용하여 숫자형의 char을 int형으로 변환하여 해당 숫자를 리스트에 추가한다.

Collections.sort(numbers): 리스트의 숫자들을 오름차순으로 정렬한다.

numbers.stream().mapToInt(i -> i).toArray(): 정렬된 리스트를 배열로 변환한다.

**코드 장점**

숫자 추출 및 정렬이 간편: 숫자 추출 및 정렬을 위해 자바의 내장 함수와 컬렉션을 활용하여 간편한 코드를 제공한다.

**코드 단점**

숫자 범위 제한: 코드는 문자열에서 0부터 9까지의 숫자만 추출하고 정렬한다.

만약 다른 숫자 범위가 필요한 경우 코드를 수정해야 한다.
