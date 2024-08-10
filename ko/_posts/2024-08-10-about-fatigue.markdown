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

XX게임에는 피로도 시스템(0 이상의 정수로 표현합니다)이 있으며, 일정 피로도를 사용해서 던전을 탐험할 수 있습니다.

이때, 각 던전마다 탐험을 시작하기 위해 필요한 "최소 필요 피로도"와 던전 탐험을 마쳤을 때 소모되는 "소모 피로도"가 있습니다.

"최소 필요 피로도"는 해당 던전을 탐험하기 위해 가지고 있어야 하는 최소한의 피로도를 나타내며, "소모 피로도"는 던전을 탐험한 후 소모되는 피로도를 나타냅니다.

예를 들어 "최소 필요 피로도"가 80, "소모 피로도"가 20인 던전을 탐험하기 위해서는 유저의 현재 남은 피로도는 80 이상 이어야 하며, 던전을 탐험한 후에는 피로도 20이 소모됩니다.

이 게임에는 하루에 한 번씩 탐험할 수 있는 던전이 여러개 있는데, 한 유저가 오늘 이 던전들을 최대한 많이 탐험하려 합니다.

유저의 현재 피로도 k와 각 던전별 "최소 필요 피로도", "소모 피로도"가 담긴 2차원 배열 dungeons 가 매개변수로 주어질 때, 유저가 탐험할수 있는 최대 던전 수를 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- k는 1 이상 5,000 이하인 자연수입니다.
- dungeons의 세로(행) 길이(즉, 던전의 개수)는 1 이상 8 이하입니다.
- dungeons의 가로(열) 길이는 2 입니다.
- dungeons의 각 행은 각 던전의 ["최소 필요 피로도", "소모 피로도"] 입니다.
- "최소 필요 피로도"는 항상 "소모 피로도"보다 크거나 같습니다.
- "최소 필요 피로도"와 "소모 피로도"는 1 이상 1,000 이하인 자연수입니다.
- 서로 다른 던전의 ["최소 필요 피로도", "소모 피로도"]가 서로 같을 수 있습니다.

#### 입출력 예시

| k   | dungeons                  | result |
| --- | ------------------------- | ------ |
| 80  | [[80,20],[50,40],[30,10]] | 3      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int answer = 0;
    public boolean[] visit;

    public int solution(int k, int[][] dungeons) {
        visit = new boolean[dungeons.length];

        dfs(0, k, dungeons);

        return answer;
    }

    public void dfs(int depth, int k, int[][] dungeons) {
        for (int i = 0; i < dungeons.length; i++) {
            if(visit[i] || dungeons[i][0] > k){
                continue;
            } else{
                visit[i] = true;
                dfs(depth + 1, k - dungeons[i][1], dungeons);
                visit[i] = false;
            }
        }
        answer = Math.max(answer, depth);
    }
}
```

### 풀이 설명

만약 최소 필요도가 큰 순서대로 한다면, [80,20],[50,40],[30,10]인데 3번째 던전을 탐색할 수 없기 때문에 불가능하고, 소모 피로도가 적은 순서대로 한다면, [30,10], [80,20],[50,40]인데 첫 번째 던전을 돌면 남은 필요도는 70이기 때문에 두 번째 던전을 탐색할 수 없기에 불가능합니다.

즉, 완전탐색을 사용해 모든 경우의 수를 탐색하는 방법 밖에 없어 재귀함수를 이용한 DFS로 풀이했습니다.

dfs 메서드는 재귀적으로 호출됩니다.

각 호출은 현재까지의 탐색 깊이(depth), 현재 레벨(k), 그리고 던전 정보 배열(dungeons)을 인수로 받습니다.

반복문을 통해 방문하지 않은 던전 중에서 요구 레벨이 현재 레벨 이하인 던전을 탐색합니다.

방문하지 않은 던전 중에서 가장 먼저 발견된 던전을 방문하고, 해당 던전의 요구 레벨을 현재 레벨에서 뺀 값으로 재귀 호출합니다.

재귀 호출이 종료되면 해당 던전의 방문 여부를 다시 false로 변경합니다.

### 결론

모든 던전을 탐색하면서 최대 탐색 깊이를 기록하고, 이를 최종적으로 반환합니다.
이 코드는 DFS 알고리즘을 이용하여 모든 가능한 경로를 탐색하고, 그 중에서 최대 탐색 깊이를 구하는 간단한 방법을 제시합니다.
