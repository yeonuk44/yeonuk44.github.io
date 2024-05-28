---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_String_Push
title: 문자열 밀기 (with.Java)
# title: String push (with.Java)
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
date: 2024-05-26 09:00:00 +0900
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

## "문자열 밀기 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 "hello"에서 각 문자를 오른쪽으로 한 칸씩 밀고 마지막 문자는 맨 앞으로 이동시키면 "ohell"이 됩니다.

이것을 문자열을 민다고 정의한다면 문자열 A와 B가 매개변수로 주어질 때, A를 밀어서 B가 될 수 있다면 밀어야 하는 최소 횟수를 return하고 밀어서 B가 될 수 없으면 -1을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 0 < A의 길이 = B의 길이 < 100
- A, B는 알파벳 소문자로 이루어져 있습니다.

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| A       | B       | result |
| ------- | ------- | ------ |
| "hello" | "ohell" | 1      |
| "apple" | "elppa" | -1     |
| "atat"  | "tata"  | 1      |
| "abc"   | "abc"   | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String A, String B) {
        int answer = -1;
        StringBuilder sb = new StringBuilder(A);
        char[] chArr = A.toCharArray();
        int repeatCount = 1;

        if(A.equals(B)){
            return 0;
        }

        for(int i = chArr.length - 1; i >= 0; i--){
            sb.replace(0,0,Character.toString(chArr[i]));
            sb.deleteCharAt(sb.length() - 1);
            if(sb.toString().equals(B)){
                return repeatCount;
            }
            repeatCount++;
        }


        return answer;
    }
}
```

### 풀이 리뷰

문자열을 회전시켜서 원하는 문자열을 만들기 위한 최소 회전 횟수를 구하는 문제를 해결하기 위해 문자열을 조작하는 방식을 사용합니다.

위의 코드는 두 문자열 A와 B가 주어졌을 때, 문자열 A를 순환 이동하여 B와 동일한 문자열을 만들기 위해 필요한 최소 회전 횟수를 계산하는 함수입니다.

먼저, 입력된 문자열 A와 B가 동일한 경우에는 회전할 필요가 없으므로 0을 반환합니다.

그렇지 않은 경우, 문자열 A를 StringBuilder를 사용하여 문자열을 조작합니다.

문자열 A의 문자 배열을 만들어서 뒤에서부터 앞으로 순차적으로 문자열을 조작합니다.

각 회전마다 문자열 A를 순환 이동하여 B와 비교합니다.

문자열 A가 B와 동일해지는 순간에는 현재까지의 회전 횟수를 반환합니다.
만약 문자열 A를 순환 이동하여 B와 동일한 문자열을 찾지 못하면, -1을 반환합니다.
