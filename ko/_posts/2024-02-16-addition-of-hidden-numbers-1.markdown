---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Addition_Of_Hidden_Numbers_1
title: 숨어있는 숫자의 덧셈 1 (with.Java)
# title: Addition of hidden numbers 1 (with.Java)
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
date: 2024-02-16 09:00:00 +0900
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

## "숨어있는 숫자의 덧셈 1" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 my_string이 매개변수로 주어집니다.

my_string안의 모든 자연수들의 합을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ my_string의 길이 ≤ 1,000
- my_string은 소문자, 대문자 그리고 한자리 자연수로만 구성되어있습니다.

#### 입출력 예시

| my_string       | result |
| --------------- | ------ |
| "aAb1B2cC34oOp" | 10     |
| "1a2b3c4d123"   | 16     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String my_string) {
        int answer = 0;
        for (char ch : my_string.toCharArray()) {
            if (Character.isDigit(ch)) {
                answer += Character.getNumericValue(ch);
            }
        }
        return answer;
    }
}
```

### 풀이 설명

- solution(String my_string): 주어진 문자열 my_string에서 숫자를 추출하고, 추출한 숫자들을 더한 결과를 반환한다.
- int answer: 최종 결과를 저장할 변수.
- 문자열을 순회하면서 Character.isDigit(ch)를 사용하여 각 문자가 숫자인지 확인하고, 숫자라면 Character.getNumericValue(ch)를 사용하여 해당 숫자를 누적하여 더한다.
- 최종적으로 더해진 값을 반환한다.

**코드 장점**

- 숫자 합산이 간편: 각 문자에서 숫자를 추출하여 더하는 과정이 간편하고 직관적이다.

**코드 단점**

- 숫자 범위 제한: 코드는 문자열에서 0부터 9까지의 숫자만 추출하여 더한다. 만약 - 다른 숫자 범위가 필요한 경우 코드를 수정해야 한다.
