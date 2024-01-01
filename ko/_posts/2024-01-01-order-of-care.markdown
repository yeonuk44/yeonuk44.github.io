---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Order_Of_Care
title: 진료 순서 정하기(with.Java)
# title: Order of Care (with.Java)
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
date: 2024-01-01 09:00:00 +0900
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

## "진료 순서 정하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

우주여행을 하던 머쓱이는 엔진 고장으로 PROGRAMMERS-962 행성에 불시착하게 됐습니다.

입국심사에서 나이를 말해야 하는데, PROGRAMMERS-962 행성에서는 나이를 알파벳으로 말하고 있습니다. a는 0, b는 1, c는 2, ..., j는 9입니다.

예를 들어 23살은 cd, 51살은 fb로 표현합니다. 나이 age가 매개변수로 주어질 때 PROGRAMMER-962식 나이를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

age는 자연수입니다.

age ≤ 1,000

PROGRAMMERS-962 행성은 알파벳 소문자만 사용합니다.

#### 입출력 예시

| age | result |
| --- | ------ |
| 23  | "cd"   |
| 51  | "fb"   |
| 100 | "baa"  |

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(int age) {
        String answer = "";
        for (int i = 0; i < Integer.toString(age).length(); i++) {
            answer += (char) ((char) Integer.toString(age).charAt(i) + 49);
        }

        return answer;
    }
}
```

#### 풀이 설명

이 코드는 주어진 자연수 age를 각 자리 숫자를 알파벳으로 매핑하여 문자열로 반환하는 함수입니다. 코드를 간략하게 해설하면 다음과 같습니다:

String answer = "";: 결과를 저장할 빈 문자열 answer를 초기화합니다.

for (int i = 0; i < Integer.toString(age).length(); i++) : 주어진 숫자 age를 문자열로 변환하고, 문자열의 각 자리에 대해 반복하는 for 루프를 설정합니다.

answer += (char)((char) Integer.toString(age).charAt(i) + 49);: 현재 자릿수의 문자를 ASCII 값으로 변환하고, 그 값에 49를 더한 값을 다시 문자로 변환하여 answer에 추가합니다.

여기서 49를 더한 이유는 각 숫자에 49를 더하면 그에 해당하는 ASCII 코드의 알파벳이 됩니다. (0에 49를 더하면 'a', 1에 49를 더하면 'b', ..., 9에 49를 더하면 'j'가 됨)

return answer;: 변환된 문자열을 반환합니다.

코드는 각 자리 숫자를 알파벳으로 변환하는 간단한 방식을 사용하고 있습니다.

예를 들어, 23이 주어지면 "cd"를 반환하게 됩니다. 코드가 문자열을 처리하고 각 자릿수를 변환하는 데에는 반복문을 활용하고 있습니다.

아스키 코드에 대해서도 간단히 알아보겠습니다.

##### 아스키 코드란?

아스키 코드(ASCII 코드)는 컴퓨터에서 문자를 표현하기 위해 사용되는 표준 인코딩 체계입니다.

ASCII는 "American Standard Code for Information Interchange"의 약자로, 미국에서 최초로 개발되었습니다.

ASCII 코드는 7비트로 문자를 표현하며, 0부터 127까지 총 128개의 문자를 포함합니다.

이 코드는 주로 영문 알파벳, 숫자, 특수문자 등을 포함하고 있습니다. 예를 들면 다음과 같습니다:

아스키 코드 예시

영문 대문자: A-Z (65부터 90까지)

영문 소문자: a-z (97부터 122까지)

숫자: 0-9 (48부터 57까지)

특수문자: !, @, #, $, %, 등

###### 정리

ASCII 코드는 컴퓨터 간에 문자를 교환하고 표현하기 위한 표준으로 널리 사용되며, 많은 프로그래밍 언어에서도 이를 기반으로 문자를 다룹니다.

ASCII 코드는 확장 ASCII나 유니코드와 같은 다양한 문자 인코딩 체계의 기반으로도 활용되고 있습니다.
