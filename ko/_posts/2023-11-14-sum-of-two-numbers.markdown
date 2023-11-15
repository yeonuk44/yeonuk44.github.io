---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sum_Of_Two_Numbers
title: 두 수의 합(with.Java)
# title: Sum of two numbers (with.Java)
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
date: 2023-11-14 09:00:00 +0900
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

### "두 수의 합" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

0 이상의 두 정수가 문자열 a, b로 주어질 때, a + b의 값을 문자열로 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| a                      | b                       | result                  |
| ---------------------- | ----------------------- | ----------------------- |
| "582"                  | "734"                   | "1316"                  |
| "18446744073709551615" | "287346502836570928366" | "305793246910280479981" |
| "0"                    | "0"                     | "0"                     |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String a, String b) {
        String answer = "";
        int intA = Integer.parseInt(a);
        int intB = Integer.parseInt(b);
        int sum = intA + intB;
        answer = String.valueOf(sum);
        return answer;
    }
}
```

##### 풀이 설명

처음엔 Integer 데이터 타입으로 변환하여 더하고 다시 문자열로 변환하여 반환하는 코드를 작성했으나 Testcase 2번의 18446744073709551615 해당 정수가 너무 큰 수이기에 통과하지 않았습니다.

이후 Integer 데이터 타입의 2배의 크기를 가진 long을 사용하여 문제를 풀었습니다.

#### long을 활용한 풀이

```java
class Solution {
    public String solution(String a, String b) {
        String answer = "";
        long longA = Long.parseLong(a);
        long longB = Long.parseLong(b);
        long sum = longA + longB;
        answer = String.valueOf(sum);
        return answer;
    }
}
```

그러나 long 데이터 타입을 사용해도 Testcase 2번의 18446744073709551615을 통과할 수 없었습니다.

너무 큰 수이기 때문입니다.

이에 BigInteger 클래스를 사용해 아주 큰 정수 값을 처리했습니다.

#### BigInteger를 활용한 풀이

```java
import java.math.BigInteger;

public class Solution {
    public String solution(String a, String b) {
        String answer = "";
        BigInteger bigA = new BigInteger(a);
        BigInteger bigB = new BigInteger(b);
        BigInteger sum = bigA.add(bigB);
        answer = sum.toString();
        return answer;
    }
}
```

위 코드에서는 입력된 두 문자열을 BigInteger 객체로 변환하고, add 메서드를 사용하여 더합니다.

그런 다음 toString 메서드를 사용하여 결과를 문자열로 변환하여 반환합니다.

이렇게 하면 아주 큰 정수 값을 정확하게 처리할 수 있습니다.
