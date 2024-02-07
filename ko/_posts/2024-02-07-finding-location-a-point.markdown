---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_Location_A_Point
title: 점의 위치 구하기(with.Java)
# title: Finding the location of a point (with.Java)
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
date: 2024-02-07 09:00:00 +0900
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

## "점의 위치 구하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

사분면은 한 평면을 x축과 y축을 기준으로 나눈 네 부분입니다.

사분면은 아래와 같이 1부터 4까지 번호를매깁니다.

x 좌표와 y 좌표가 모두 양수이면 제1사분면에 속합니다.

x 좌표가 음수, y 좌표가 양수이면 제2사분면에 속합니다.

x 좌표와 y 좌표가 모두 음수이면 제3사분면에 속합니다.

x 좌표가 양수, y 좌표가 음수이면 제4사분면에 속합니다.

x 좌표 (x, y)를 차례대로 담은 정수 배열 dot이 매개변수로 주어집니다.

좌표 dot이 사분면 중 어디에 속하는지 1, 2, 3, 4 중 하나를 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- dot의 길이 = 2
- dot[0]은 x좌표를, dot[1]은 y좌표를 나타냅니다
- -500 ≤ dot의 원소 ≤ 500
- dot의 원소는 0이 아닙니다.

#### 입출력 예시

| dot     | result |
| ------- | ------ |
| [2, 4]  | 1      |
| [-7, 9] | 2      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] dot) {
        int answer = 0;

        if(dot[0] > 0 && dot[1] > 0){
            answer = 1;
        }else if(dot[0] < 0 && dot[1] > 0){
            answer = 2;
        }else if(dot[0] < 0 && dot[1] < 0){
            answer = 3;
        }else if(dot[0] > 0 && dot[1] < 0){
            answer = 4;
        }
        return answer;
    }
}
```

### 풀이 설명

해당 코드는 주어진 좌표 dot이 속하는 사분면을 판별하여 반환하는 코드입니다.

특별한 함수를 사용하지 않았으며, 주어진 조건문을 통해 사분면을 결정하고 해당 값을 answer에 저장합니다.

여기서 사용된 주요 개념은 좌표 평면에서의 사분면을 구분하는 것입니다.

각 조건문은 다음을 의미합니다:

dot[0] > 0 && dot[1] > 0: 제 1 사분면
dot[0] < 0 && dot[1] > 0: 제 2 사분면
dot[0] < 0 && dot[1] < 0: 제 3 사분면
dot[0] > 0 && dot[1] < 0: 제 4 사분면

**이 코드의 장점**

간단하고 명확한 로직: 주어진 조건들을 명시적으로 표현하여 이해하기 쉽습니다.

성능: 각 조건에 대한 판별이 순차적으로 이루어지기 때문에 매우 효율적입니다.

**단점**

일부 경우에 따라 dot 배열의 크기가 잘못된 경우가 있을 수 있습니다.

이러한 상황에 대한 처리가 없습니다. (예: dot.length가 2가 아닌 경우)
