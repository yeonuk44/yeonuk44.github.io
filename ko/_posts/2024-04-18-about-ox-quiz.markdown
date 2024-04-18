---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_OX_Quiz
title: OX퀴즈 (with.Java)
# title: OX Quiz (with.Java)
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
date: 2024-04-18 09:00:00 +0900
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

## "OX퀴즈 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

덧셈, 뺄셈 수식들이 'X [연산자] Y = Z' 형태로 들어있는 문자열 배열 quiz가 매개변수로 주어집니다.

수식이 옳다면 "O"를 틀리다면 "X"를 순서대로 담은 배열을 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 연산 기호와 숫자 사이는 항상 하나의 공백이 존재합니다. 단 음수를 표시하는 마이너스 기호와 숫자 사이에는 공백이 존재하지 않습니다.
- 1 ≤ quiz의 길이 ≤ 10
- X, Y, Z는 각각 0부터 9까지 숫자로 이루어진 정수를 의미하며, 각 숫자의 맨 앞에 마이너스 기호가 하나 있을 수 있고 이는 음수를 의미합니다.
- X, Y, Z는 0을 제외하고는 0으로 시작하지 않습니다.
- 10,000 ≤ X, Y ≤ 10,000
- 20,000 ≤ Z ≤ 20,000
- [연산자]는 + 와 - 중 하나입니다.

#### 입출력 예시

| my_string                                                  | num1                 |
| ---------------------------------------------------------- | -------------------- |
| ["3 - 4 = -3", "5 + 6 = 11"]                               | ["X", "O"]           |
| ["19 - 6 = 13", "5 + 66 = 71", "5 - 15 = 63", "3 - 1 = 2"] | ["O", "O", "X", "O"] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public String[] solution(String[] quiz) {
        String[] answer = new String[quiz.length];
        String[] temp = new String[quiz.length];

        for(int i = 0; i < quiz.length; i++){
            temp = quiz[i].split(" ");

            if(temp[1].equals("+")){
                if(Integer.valueOf(temp[0]) + Integer.valueOf(temp[2]) == Integer.valueOf(temp[4])){
                    answer[i] = "O";
                }else{
                    answer[i] = "X";
                }
            }

            if(temp[1].equals("-")){
                if(Integer.valueOf(temp[0]) - Integer.valueOf(temp[2]) == Integer.valueOf(temp[4])){
                    answer[i] = "O";
                }else{
                    answer[i] = "X";
                }
            }
        }
        return answer;
    }
}
```

### 풀이 설명

solution 메서드는 주어진 quiz 배열의 각 요소를 분석하여 결과를 저장할 answer 배열을 초기화합니다.

또한 임시로 사용할 temp 배열도 초기화합니다.

그런 다음 for 루프를 통해 quiz 배열의 각 요소를 처리합니다.

각 요소는 공백을 기준으로 분할되어 temp 배열에 저장됩니다.

temp 배열의 두 번째 요소가 "+"인 경우, 첫 번째 요소와 세 번째 요소를 정수로 변환하여 더한 값이 다섯 번째 요소와 같은지 확인합니다.

같다면 answer 배열의 해당 인덱스에 "O"를 저장하고, 다르다면 "X"를 저장합니다.

temp 배열의 두 번째 요소가 "-"인 경우에도 같은 방식으로 처리합니다.

마지막으로 answer 배열을 반환합니다.
