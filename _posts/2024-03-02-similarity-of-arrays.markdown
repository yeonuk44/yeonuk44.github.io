---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Similarity_Of_Arrays
title: Similarity of arrays (with.Java)
# title: Similarity of arrays (with.Java)
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
date: 2024-03-02 09:00:00 +0900
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

## "문자열 계산하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

my_string은 "3 + 5"처럼 문자열로 된 수식입니다.

문자열 my_string이 매개변수로 주어질 때, 수식을 계산한 값을 return 하는 solution 함수를 완성해주세요.

#### 제한사항

- 연산자는 +, -만 존재합니다.
- 문자열의 시작과 끝에는 공백이 없습니다.
- 0으로 시작하는 숫자는 주어지지 않습니다.
- 잘못된 수식은 주어지지 않습니다.
- 5 ≤ my_string의 길이 ≤ 100
- my_string을 계산한 결과값은 1 이상 100,000 이하입니다.
- my_string의 중간 계산 값은 -100,000 이상 100,000 이하입니다.
- 계산에 사용하는 숫자는 1 이상 20,000 이하인 자연수입니다.
- my_string에는 연산자가 적어도 하나 포함되어 있습니다.
- return type 은 정수형입니다.
- my_string의 숫자와 연산자는 공백 하나로 구분되어 있습니다.

#### 입출력 예시

| my_string | result |
| --------- | ------ |
| "3 + 4"   | 7      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String my_string) {
        String[] strArr = my_string.split(" ");
        int answer = Integer.parseInt(strArr[0]);

        for(int i = 0; i < strArr.length - 1; i++){
            if(strArr[i].equals("+")){
                answer += Integer.parseInt(strArr[i + 1]);
            }else if(strArr[i].equals("-")){
                answer -= Integer.parseInt(strArr[i + 1]);
            }
        }
        return answer;
    }
}
```

### 풀이 설명

- 함수는 문자열을 입력받아 공백을 기준으로 문자열을 분리한 후, 첫 번째 값을 정수로 변환하여 초기값으로 설정합니다. 그리고 반복문을 통해 연산자와 피연산자를 확인하고 계산을 수행합니다.
- "+" 연산자인 경우, 현재 값에 다음 값을 더합니다.
- "-" 연산자인 경우, 현재 값에서 다음 값을 뺍니다.
- 최종적으로 계산된 결과를 반환합니다.
- 이 코드는 간단한 사칙연산을 수행하는 계산기 함수로 사용할 수 있습니다. 예를 들어 "10 + 5 - 3"과 같은 문자열을 입력하면, 10 + 5 - 3 = 12의 결과를 반환합니다.
- 주의할 점은 입력된 문자열이 유효한 형식인지 검증하는 로직이 없으므로, 잘못된 입력이 주어지면 예기치 않은 동작을 할 수 있다는 점이 있습니다.
