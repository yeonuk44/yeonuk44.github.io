---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sharing_A_Pizza_1
title: 피자 나눠 먹기 1 (with.Java)
# title: Sharing a Pizza 1 (with.Java)
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
date: 2024-01-05 09:00:00 +0900
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

## "피자 나눠 먹기 1" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이네 피자가게는 피자를 일곱 조각으로 잘라 줍니다.

피자를 나눠먹을 사람의 수 n이 주어질 때, 모든 사람이 피자를 한 조각 이상 먹기 위해 필요한 피자의 수를 return 하는 solution 함수를 완성해보세요.

#### 입출력 예시

| n   | result |
| --- | ------ |
| 7   | 1      |
| 1   | 1      |
| 15  | 3      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        if(n % 7 == 0){
            answer = n / 7;
        }else{
            answer = n / 7 + 1;
        }
        return answer;
    }
}
```

#### 풀이 설명

public int solution(int n) : 함수 solution을 선언하고, 양수 정수 n을 입력 매개변수로 받습니다. 이 함수는 정수 값을 반환합니다.

int answer = 0;: 정수 변수 answer를 선언하고 0으로 초기화합니다. 이 변수는 결과를 저장할 것입니다.

if (n % 7 == 0) : 입력된 정수 n을 7로 나누었을 때 나머지가 0인 경우, 즉 n이 7의 배수인 경우, 아래의 작업을 수행합니다.

answer = n / 7;: answer 변수에 n을 7로 나눈 몫을 저장합니다. 이렇게 하면 7의 배수인 경우, 몫이 정확한 값을 나타냅니다.

else : 7의 배수가 아닌 경우, 즉 n이 7의 배수가 아닌 경우, 아래의 작업을 수행합니다.

answer = n / 7 + 1;: answer 변수에 n을 7로 나눈 몫에 1을 더한 값을 저장합니다. 이렇게 하면 나머지가 있는 경우, 다음 정수로 반올림한 값을 나타냅니다.

return answer;: 최종 결과인 answer 값을 함수의 반환 값으로 반환합니다.
