---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_Composite_Number
title: Find composite number (with.Java)
# title: Find composite number (with.Java)
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
date: 2024-02-11 09:00:00 +0900
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

## "주사위의 개수" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 직육면체 모양의 상자를 하나 가지고 있는데 이 상자에 정육면체 모양의 주사위를 최대한 많이 채우고 싶습니다.

상자의 가로, 세로, 높이가 저장되어있는 배열 box와 주사위 모서리의 길이 정수 n이 매개변수로 주어졌을 때, 상자에 들어갈 수 있는 주사위의 최대 개수를 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- box의 길이는 3입니다.
- box[0] = 상자의 가로 길이
- box[1] = 상자의 세로 길이
- box[2] = 상자의 높이 길이
- 1 ≤ box의 원소 ≤ 100
- 1 ≤ n ≤ 50
- n ≤ box의 원소
- 주사위는 상자와 평행하게 넣습니다.

#### 입출력 예시

| box        | n   | result |
| ---------- | --- | ------ |
| [1, 1, 1]  | 1   | 1      |
| [10, 8, 6] | 3   | 12     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] box, int n) {
        int answer = 0;
        int x = box[0] / n;
        int y = box[1] / n;
        int z = box[2] / n;

        answer = x * y * z;
        return answer;
    }
}
```

### 풀이 설명

이 문제는 박스의 크기와 나누려는 수가 주어졌을 때, 박스의 부피를 계산하는 문제입니다.

문제를 해결하기 위해서는 주어진 박스의 크기를 각 차원(x, y, z)별로 나누어야 합니다.

그리고 나서 각 차원별로 나눈 값을 곱하여 최종적인 부피를 계산할 수 있습니다.

box 배열의 각 차원(x, y, z)을 n으로 나누어 각 차원별로 나눈 값을 구합니다.

나눈 값을 곱하여 최종적인 부피를 계산합니다.
