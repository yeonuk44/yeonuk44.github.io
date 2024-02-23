---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Uppercase_And_Lowercase_Letters
title: 대문자와 소문자(with.Java)
# title: Uppercase and lowercase letters (with.Java)
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
date: 2024-02-23 09:00:00 +0900
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
- 1 ≤ code ≤ cipher의 길이
- cipher는 소문자와 공백으로만 구성되어 있습니다.
- 공백도 하나의 문자로 취급합니다.

#### 입출력 예시

| cipher                     | code | result     |
| -------------------------- | ---- | ---------- |
| "dfjardstddetckdaccccdegk" | 4    | "attack"   |
| "pfqallllabwaoclk"         | 2    | "fallback" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String cipher, int code) {
        StringBuilder sb = new StringBuilder();
        int max = cipher.length() / code;
        for(int i = 1; i <= max; i++){
            int temp = i * code;
            sb.append(cipher.charAt(temp - 1));
        }
        return sb.toString();
    }
}
```

### 풀이 설명

먼저, StringBuilder 객체인 sb를 생성합니다. 이 객체는 문자열을 효율적으로 처리하기 위해 사용됩니다.

다음으로, cipher의 길이를 code로 나눈 값을 max에 저장합니다. 이는 추출할 문자의 개수를 나타냅니다.

그리고 for 루프를 통해 1부터 max까지의 숫자를 반복합니다. 이는 추출할 문자의 위치를 나타냅니다.

루프 내부에서는 temp 변수에 i와 code를 곱한 값을 저장합니다. 이는 추출할 문자의 인덱스를 계산하는데 사용됩니다.

그리고 sb에 cipher.charAt(temp - 1)을 추가합니다. charAt 메서드는 주어진 인덱스에 해당하는 문자를 반환합니다. temp - 1은 인덱스가 0부터 시작하는 반면, temp는 1부터 시작하기 때문에 1을 빼줍니다.

마지막으로, sb.toString()을 호출하여 StringBuilder 객체를 문자열로 변환한 후 반환합니다.

이렇게 하면 cipher 문자열에서 code 간격으로 추출된 문자들이 순서대로 이어진 새로운 문자열이 반환됩니다.
