---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Choosing_A_Multiple_Of_N
title: n의 배수 고르기 (with.Java)
# title: Choosing a multiple of n (with.Java)
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
date: 2024-03-04 09:00:00 +0900
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

## "숫자 찾기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

정수 num과 k가 매개변수로 주어질 때, num을 이루는 숫자 중에 k가 있으면 num의 그 숫자가 있는 자리 수를 return하고 없으면 -1을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 0 < num < 1,000,000
- 0 ≤ k < 10
- num에 k가 여러 개 있으면 가장 처음 나타나는 자리를 return 합니다.

#### 입출력 예시

| num    | k   | result |
| ------ | --- | ------ |
| 29183  | 1   | 3      |
| 232443 | 4   | 4      |
| 123456 | 7   | -1     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public int solution(int num, int k) {
        int answer = 0;
        char[] chArr = String.valueOf(num).toCharArray();
        char chK = (char) (k + '0');

        for(int i = 0; i < chArr.length; i++){
            if(chArr[i] == chK){
                answer = i + 1;
                break;
            }
        }
        if(answer == 0) answer = -1;
        return answer;
    }
}
```

### 풀이 설명

- answer 변수를 0으로 초기화합니다. 이 변수는 k가 처음으로 등장하는 위치를 저장하는 역할을 합니다.
- num을 String으로 변환한 후, toCharArray() 메소드를 사용하여 각 자리의 숫자를 char 배열로 변환합니다.
- chK 변수에는 k를 char 형태로 변환한 값을 저장합니다.
- for 문을 사용하여 chArr 배열을 순회하면서 chK와 같은 숫자가 있는지 확인합니다.
- chArr[i]와 chK가 같으면, answer에 i + 1의 값을 저장하고 반복문을 종료합니다. 이때, i + 1은 1부터 시작하는 위치를 의미합니다.
- 반복문이 종료된 후, answer가 0인 경우는 k가 주어진 숫자에 없는 경우이므로 -1을 저장합니다.
- 최종적으로 answer 값을 반환합니다.
