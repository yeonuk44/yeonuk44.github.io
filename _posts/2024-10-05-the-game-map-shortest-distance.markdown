---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Game_Map_Shortest_Distance
title: game map shortest distance (with.Java)
# title: game map shortest distance (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, dfs]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-05 09:00:00 +0900
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

## 게임 맵 최단거리(with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

n개의 음이 아닌 정수들이 있습니다.

이 정수들을 순서를 바꾸지 않고 적절히 더하거나 빼서 타겟 넘버를 만들려고 합니다.

예를 들어 [1, 1, 1, 1, 1]로 숫자 3을 만들려면 다음 다섯 방법을 쓸 수 있습니다.

-1+1+1+1+1 = 3

+1-1+1+1+1 = 3

+1+1-1+1+1 = 3

+1+1+1-1+1 = 3

+1+1+1+1-1 = 3

사용할 수 있는 숫자가 담긴 배열 numbers, 타겟 넘버 target이 매개변수로 주어질 때 숫자를 적절히 더하고 빼서 타겟 넘버를 만드는 방법의 수를 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- 주어지는 숫자의 개수는 2개 이상 20개 이하입니다.
- 각 숫자는 1 이상 50 이하인 자연수입니다.
- 타겟 넘버는 1 이상 1000 이하인 자연수입니다.

#### 입출력 예

<!-- | prices          | return          |
| --------------- | --------------- |
| [1, 2, 3, 2, 3] | [4, 3, 1, 1, 0] | -->

| numbers         | target | return |
| --------------- | ------ | ------ |
| [1, 1, 1, 1, 1] | 3      | 5      |
| [4, 1, 2, 1]    | 4      | 2      |

### 문제 풀이

```java
class Solution {
    static int answer;
    public int solution(int[] numbers, int target) {
        answer = 0;
        dfs(numbers, target, 0, 0);
        return answer;
    }
    public void dfs(int[] numbers, int target, int depth, int total){
        if(numbers.length == depth){
            if(total == target){
                answer++;
            }
        }else{
            dfs(numbers, target, depth + 1, total + numbers[depth]);
            dfs(numbers, target, depth + 1, total - numbers[depth]);
        }
    }
}
```

#### 풀이 설명

1. 클래스와 변수 선언
   class Solution: 문제를 해결하기 위한 클래스입니다.
   static int answer: 정적 변수 answer는 타겟 넘버를 만들 수 있는 경우의 수를 저장합니다.
2. solution 메서드
   public int solution(int[] numbers, int target): 주어진 숫자 배열 numbers와 목표 숫자 target을 입력으로 받아 타겟 넘버를 만들 수 있는 경우의 수를 반환합니다.
   answer = 0: 경우의 수를 초기화합니다.
   dfs(numbers, target, 0, 0): 깊이 우선 탐색을 시작합니다. 초기 깊이는 0, 초기 합계도 0으로 설정합니다.
   return answer: 최종적으로 계산된 경우의 수를 반환합니다.
3. dfs 메서드
   public void dfs(int[] numbers, int target, int depth, int total): 깊이 우선 탐색을 수행하는 재귀 메서드입니다.
   if(numbers.length == depth): 배열의 끝에 도달했는지 확인합니다.
   if(total == target): 현재 합계 total이 목표 숫자 target과 같으면 경우의 수를 증가시킵니다.
   else: 배열의 끝에 도달하지 않았다면 다음 단계로 넘어갑니다.
   dfs(numbers, target, depth + 1, total + numbers[depth]): 현재 숫자를 더한 경우를 탐색합니다.
   dfs(numbers, target, depth + 1, total - numbers[depth]): 현재 숫자를 뺀 경우를 탐색합니다.

#### 결론

이 코드는 DFS를 사용하여 모든 가능한 경우를 탐색하고, 목표 숫자와 일치하는 경우의 수를 계산합니다.

주어진 숫자 배열과 목표 숫자가 주어졌을 때, 이 코드를 통해 타겟 넘버를 만들 수 있는 모든 경우의 수를 효율적으로 구할 수 있습니다.
