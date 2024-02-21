---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Close_Number
title: 가까운 수(with.Java)
# title: Close number(with.Java)
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
date: 2024-02-21 09:00:00 +0900
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

## "369 게임" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 친구들과 369게임을 하고 있습니다.

369게임은 1부터 숫자를 하나씩 대며 3, 6, 9가 들어가는 숫자는 숫자 대신 3, 6, 9의 개수만큼 박수를 치는 게임입니다.

머쓱이가 말해야하는 숫자 order가 매개변수로 주어질 때, 머쓱이가 쳐야할 박수 횟수를 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 1 ≤ order ≤ 1,000,000

#### 입출력 예시

| order | result |
| ----- | ------ |
| 3     | 1      |
| 29423 | 2      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int solution(int order) {
        int answer = 0;

        for(char str : Integer.toString(order).toCharArray()){
            int temp = str - '0';
            if(temp - 3 == 0 || temp - 6 == 0 || temp - 9 == 0){
                answer++;
            }
        }
        return answer;
    }
}
```

### 풀이 설명

int temp = str - '0';에서 '0'을 빼는 이유는 문자형으로 된 숫자를 정수형으로 변환하기 위해서입니다.

문자형 숫자는 ASCII 코드 값으로 표현되는데, 숫자 '0'의 ASCII 코드 값은 48입니다.

따라서 '0'과 문자형 숫자를 뺌으로써 해당 문자형 숫자를 정수형으로 변환할 수 있습니다.

예를 들어, str이 '3'인 경우, '3' - '0'은 51 - 48로 계산됩니다. 이는 정수형 숫자 3과 같은 값을 가지게 됩니다.

즉, int temp = str - '0';은 문자형 숫자를 정수형으로 변환하는 역할을 수행합니다.
