---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Farigue
title: 피로도 (with.Java)
# title: Fatigue (with.Java)
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
date: 2024-08-10 09:00:00 +0900
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

## 피로도 (with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

Leo는 카펫을 사러 갔다가 아래 그림과 같이 중앙에는 노란색으로 칠해져 있고 테두리 1줄은 갈색으로 칠해져 있는 격자 모양 카펫을 봤습니다.

Leo는 집으로 돌아와서 아까 본 카펫의 노란색과 갈색으로 색칠된 격자의 개수는 기억했지만, 전체 카펫의 크기는 기억하지 못했습니다.

Leo가 본 카펫에서 갈색 격자의 수 brown, 노란색 격자의 수 yellow가 매개변수로 주어질 때 카펫의 가로, 세로 크기를 순서대로 배열에 담아 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- 갈색 격자의 수 brown은 8 이상 5,000 이하인 자연수입니다.
- 노란색 격자의 수 yellow는 1 이상 2,000,000 이하인 자연수입니다.
- 카펫의 가로 길이는 세로 길이와 같거나, 세로 길이보다 깁니다.

#### 입출력 예시

| brown | yellow | return |
| ----- | ------ | ------ |
| 10    | 2      | [4, 3] |
| 8     | 1      | [3, 3] |
| 24    | 24     | [8, 6] |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(int brown, int yellow) {
        int[] answer = new int[2];
        int length = brown / 2 + 1;
        int x = length;
        for(int y = 1; y < length; y++){
            if(x * y - brown == yellow){
                answer[0] = x;
                answer[1] = y;
                break;
            }
            x--;
        }
        return answer;
    }
}
```

### 풀이 설명

- solution 메서드는 정수 brown과 yellow를 입력으로 받습니다.
- answer 배열은 직사각형의 가로와 세로를 저장할 것입니다.
- length 변수에는 갈색 타일의 개수를 통해 추정한 직사각형의 가로 길이를 저장합니다.
- x에는 가로 길이를 할당합니다.
- for 루프를 사용하여 세로 길이를 1부터 length까지 탐색합니다.
- 각각의 x와 y를 곱하여 전체 타일의 수에서 갈색 타일의 수를 빼고 난 값이 노란색 타일의 수와 일치하면, 해당 x와 y값을 answer 배열에 저장하고 루프를 종료합니다.
- 만약 조건을 만족하는 x와 y가 없다면, x를 감소시키고 다시 조건을 확인합니다.
  최종적으로 answer 배열을 반환합니다.
- 이 코드는 갈색 타일과 노란색 타일의 수를 이용하여 직사각형을 만들 수 있는 경우의 가로와 세로 길이를 반환하는 문제를 해결합니다.

해설을 보충하자면, 코드는 다음과 같은 로직을 따릅니다.

- 먼저, 직사각형의 가로 길이를 구하기 위해 갈색 타일의 개수인 brown을 2로 나눈 값에 1을 더합니다. (갈색 타일은 직사각형의 가로와 세로 2줄을 각각 채우므로, 가로 길이는 반드시 세로 길이보다 크거나 같아야 합니다.)
- 가로 길이 x와 세로 길이 y를 곱한 값에서 갈색 타일의 수를 뺀 결과가 노란색 타일의 수와 일치하는지 확인합니다.
- 만약 일치한다면, 해당 가로 길이 x와 세로 길이 y를 answer 배열에 저장하고 반복문을 종료합니다.
- 그렇지 않으면, 가로 길이 x를 하나씩 감소시키면서 다시 확인합니다.
- 마지막으로, answer 배열을 반환합니다.

### 결론

이 코드는 반복문을 사용하여 가로 길이 x와 세로 길이 y를 탐색하면서 문제에서 주어진 조건을 만족시키는 경우를 찾아내고, 이를 answer 배열에 저장하여 반환합니다.
