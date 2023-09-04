---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Creating_A_Collatz_Sequence
title: 콜라츠 수열 만들기(with.Java)
# title: Creating a Collatz Sequence (with.Java)

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
date: 2023-09-04 09:00:00 +0900
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

### 9로 나눈 나머지 구현 방법에 대하여(with. Java) 알아본 글입니다.

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.
문제에 대해 먼저 알아보겠습니다.

#### 문제

음이 아닌 정수를 9로 나눈 나머지는 그 정수의 각 자리 숫자의 합을 9로 나눈 나머지와 같은 것이 알려져 있습니다.
이 사실을 이용하여 음이 아닌 정수가 문자열 number로 주어질 때, 이 정수를 9로 나눈 나머지를 return 하는 solution 함수를 작성해주세요.

##### 입출력 예시

number: "78720646226947352489"
result: 2

number는 78720646226947352489으로 각자리 숫자의 합은 101입니다.
101을 9로 나눈 나머지는 2이고, 실제로 78720646226947352489 = 9 × 8746738469660816943 + 2입니다.
따라서 2를 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String number) {
        int answer = 0;
        int temp = 0;
        for(int i = 0; i < number.length(); i++){
            temp += (number.charAt(i) - '0');
        }

        answer = temp % 9;
        return answer;
    }
}
```

##### 풀이 설명

임시로 정수 값을 저장할 temp 변수를 선언합니다.
number의 길이만큼 반복하며, temp에 number의 모든 요소를 합쳐서 저장합니다.
(number.charAt(i) - '0'); 해당 코드의 경우 1개의 문자열로 정수를 나열한 number를 character 타입으로 변환하여 하나 씩 계산하기 위해 charAt() 함수를 활용했습니다.
이 함수는 String으로 반환할 땐 그냥 사용하면 되지만, Integer형으로 반환할 땐 ASCII 로 받아져 문자열 '0' 만큼 빼주어야 우리가 의도한 정수형으로 인지됩니다.
만약 빼주지 않고 바로 정수형으로 반환받을 시, char to int로 형변환 과정에서 48이 더해진 값을 반환합니다. **'0'이 아스키 코드 값인 48이기 때문입니다.**
이렇게 반복문이 정상적으로 마치면 answer에 temp % 9 의 값을 반환하는 것으로 결과를 도출합니다.
