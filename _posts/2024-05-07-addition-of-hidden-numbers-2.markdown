---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Addition_Of_Hidden_Numbers_2
title: Addition of hidden numbers 2 (with.Java)
# title: Addition of hidden numbers 2 (with.Java)
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
date: 2024-05-07 09:00:00 +0900
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

## "다항식 더하기 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

한 개 이상의 항의 합으로 이루어진 식을 다항식이라고 합니다.

다항식을 계산할 때는 동류항끼리 계산해 정리합니다.

덧셈으로 이루어진 다항식 polynomial이 매개변수로 주어질 때, 동류항끼리 더한 결괏값을 문자열로 return 하도록 solution 함수를 완성해보세요.

같은 식이라면 가장 짧은 수식을 return 합니다.

#### 제한사항

- 0 < polynomial에 있는 수 < 100
- polynomial에 변수는 'x'만 존재합니다.
- polynomial은 양의 정수, 공백, ‘x’, ‘+'로 이루어져 있습니다.
- 항과 연산기호 사이에는 항상 공백이 존재합니다.
- 공백은 연속되지 않으며 시작이나 끝에는 공백이 없습니다.
- 하나의 항에서 변수가 숫자 앞에 오는 경우는 없습니다.
- " + 3xx + + x7 + "와 같은 잘못된 입력은 주어지지 않습니다.
- 0으로 시작하는 수는 없습니다.
- 문자와 숫자 사이의 곱하기는 생략합니다.
- polynomial에는 일차 항과 상수항만 존재합니다.
- 계수 1은 생략합니다.
- 결괏값에 상수항은 마지막에 둡니다.
- 0 < polynomial의 길이 < 50

#### 입출력 예시

<!-- | keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] | -->

| polynomial   | result   |
| ------------ | -------- |
| "3x + 7 + x" | "4x + 7" |
| "x + x + x"  | "3x"     |

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String polynomial) {
        String answer = "";
        int xNum = 0;
        int num = 0;
        String[] strArr = polynomial.split(" ");
        for(String str : strArr){
            if(str.contains("x")){
                if(str.equals("x")){
                    xNum += 1;
                }else{
                    xNum += Integer.valueOf(str.replace("x", ""));
                }
            }else if(!str.equals("+")){
                num += Integer.valueOf(str);
            }
        }

        answer = (xNum != 0 ? xNum == 1 ? "x" : xNum + "x" : "") + (num != 0 ? (xNum != 0 ? " + " : "") + num : xNum == 0 ? "0" : "");
        return answer;
    }
}
```

### 풀이 설명

- 문자열 분리: 주어진 다항식을 공백을 기준으로 분리하여 문자열 배열로 만듭니다.
- 항 처리: 각 항에 대해 반복문을 실행하고, x를 포함하는 항과 상수항을 구분하여 처리합니다.
- x를 포함하는 항: "x"만 있는 경우와 숫자와 "x"가 결합된 경우를 구분하여 x의 계수를 누적합니다.
- 상수항: "+"가 아니고 "x"를 포함하지 않는 경우에는 상수항을 누적합니다.
- 결과 문자열 생성: x의 계수와 상수항에 대한 문자열을 조합하여 최종 결과 문자열을 생성합니다.

**코드 장단점**

- 장점: 각 항을 적절히 분리하여 계산하고 결과를 문자열로 조합하는 등 다항식을 간결하게 정리하는 로직을 구현했습니다.
  코드가 간결하고 이해하기 쉽게 작성되었습니다.
- 단점: 이 코드는 입력이 주어진 형식에 맞는다고 가정합니다. 잘못된 형식의 입력이 주어지면 예외 처리가 필요합니다.
