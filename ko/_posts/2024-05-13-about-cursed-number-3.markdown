---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Cursed_Number_3
title: 저주의 숫자 3(with.Java)
# title: Cursed number 3 (with.Java)
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
date: 2024-05-13 09:00:00 +0900
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

## "저주의 숫자 3(with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

3x 마을 사람들은 3을 저주의 숫자라고 생각하기 때문에 3의 배수와 숫자 3을 사용하지 않습니다.

정수 n이 매개변수로 주어질 때, n을 3x 마을에서 사용하는 숫자로 바꿔 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ n ≤ 100

#### 입출력 예시

<!-- | keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] | -->

| n   | result |
| --- | ------ |
| 15  | 25     |
| 40  | 76     |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        for(int i = 1; i <= n; i++){
            answer++;
            while(answer % 3 == 0 || String.valueOf(answer).contains("3")){
                answer++;
            }
        }

        return answer;
    }
}
```

### 풀이 설명

answer 변수를 초기값 0으로 설정합니다.

이 변수는 결과를 나타냅니다.

i 변수를 1부터 n까지 증가시키면서 반복문을 실행합니다.

answer 변수를 1씩 증가시킵니다.

answer 변수가 3의 배수이거나, 숫자로 변환한 후에 문자열에 "3"이 포함되어 있는 동안 반복문을 실행합니다.

반복문이 실행될 때마다 answer 변수를 1씩 증가시킵니다.

반복문이 종료되면 answer 변수를 반환합니다.

**장점**

주어진 범위 내에서 3의 배수이거나 숫자에 3이 포함된 숫자의 개수를 세는 기능을 수행합니다.

코드가 간결하고 이해하기 쉽습니다.

**단점**

answer 변수를 1씩 증가시키면서 조건을 만족하는지 확인하는 방식으로 구현되어 있기 때문에, 특정 범위에서의 효율성이 낮을 수 있습니다.

answer 변수를 문자열로 변환하여 "3"이 포함되어 있는지 확인하는 과정에서 성능 저하가 발생할 수 있습니다.

**개선사항**

반복문을 사용하여 answer 변수를 1씩 증가시키는 대신, 3의 배수나 숫자에 3이 포함된 숫자를 직접 찾을 수 있는 방법을 사용하면 성능을 개선할 수 있습니다.

예를 들어, 3의 배수를 찾을 때는 3씩 증가시키면서 범위 내에서 개수를 세는 방식을 사용할 수 있습니다.

숫자에 3이 포함되어 있는지 확인할 때는 숫자를 10으로 나누어가면서 나머지를 확인하는 방식을 사용할 수 있습니다.
