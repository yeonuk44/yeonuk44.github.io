---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Immigration_Problem
title: 입국심사 (with.Java)
# title: Immigration Problem(with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, binary search]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-23 09:00:00 +0900
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

## 입국심사 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

네트워크란 컴퓨터 상호 간에 정보를 교환할 수 있도록 연결된 형태를 의미합니다.

예를 들어, 컴퓨터 A와 컴퓨터 B가 직접적으로 연결되어있고, 컴퓨터 B와 컴퓨터 C가 직접적으로 연결되어 있을 때 컴퓨터 A와 컴퓨터 C도 간접적으로 연결되어 정보를 교환할 수 있습니다.

따라서 컴퓨터 A, B, C는 모두 같은 네트워크 상에 있다고 할 수 있습니다.

컴퓨터의 개수 n, 연결에 대한 정보가 담긴 2차원 배열 computers가 매개변수로 주어질 때, 네트워크의 개수를 return 하도록 solution 함수를 작성하시오.

#### 제한사항

- 컴퓨터의 개수 n은 1 이상 200 이하인 자연수입니다.
- 각 컴퓨터는 0부터 n-1인 정수로 표현합니다.
- i번 컴퓨터와 j번 컴퓨터가 연결되어 있으면 computers[i][j]를 1로 표현합니다.
- computer[i][i]는 항상 1입니다.

<!-- #### 입출력 예

| n   | s   | result |
| --- | --- | ------ |
| 2   | 9   | [4, 5] |
| 2   | 1   | [-1]   |
| 2   | 8   | [4, 4] |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | --> -->

### 문제 풀이

```java
import java.util.Arrays;

class Solution {
    boolean[] visited;
    int answer = 0;
    public int solution(int n, int[][] computers) {

        visited = new boolean[n];
        Arrays.fill(visited, false);

        for(int i = 0; i < n; i++){
            if(visited[i] == false){
                answer++;
                dfs(i, visited, computers);
            }
        }

        return answer;
    }
    public void dfs(int idx, boolean[] visited, int[][] computers){
        visited[idx] = true;

        for(int i = 0; i < computers.length; i++){
            if(visited[i] == false && computers[idx][i] == 1){
                dfs(i, visited, computers);
            }
        }
    }
}
```

#### 풀이 설명

이 코드는 네트워크의 개수를 찾는 문제를 해결합니다.

주어진 n개의 컴퓨터와 n x n 크기의 2차원 배열 computers를 이용하여, 서로 연결된 네트워크의 수를 계산합니다.

이를 위해 깊이 우선 탐색(DFS) 알고리즘을 사용합니다.

우선, visited 배열을 선언하여 각 컴퓨터가 방문되었는지 확인합니다. 배열의 크기는 n으로 설정되고, 초기값은 모두 false로 채워집니다.

이는 모든 컴퓨터가 처음에는 방문되지 않았음을 나타냅니다.

이후, n개의 컴퓨터를 순차적으로 탐색하며, 방문되지 않은 컴퓨터를 발견할 때마다 네트워크의 수를 증가시키고, 해당 컴퓨터를 시작점으로 DFS를 수행합니다.

DFS 함수 dfs는 현재 인덱스 idx를 방문 처리한 후, 해당 컴퓨터와 연결된 다른 컴퓨터를 재귀적으로 방문합니다.

DFS는 현재 컴퓨터 idx와 연결된 모든 컴퓨터를 방문 처리합니다.

computers[idx][i] 값이 1이고, i번째 컴퓨터가 방문되지 않은 경우에만 재귀적으로 DFS를 호출합니다.

이를 통해 연결된 모든 컴퓨터를 한 네트워크로 묶어줍니다.

이 과정을 통해 모든 컴퓨터를 방문하게 되며, 새로운 네트워크를 발견할 때마다 answer를 증가시킵니다.

최종적으로, 모든 컴퓨터를 탐색한 후 answer 값을 반환하여 네트워크의 수를 출력합니다.

이 코드는 DFS 알고리즘을 사용하여 효율적으로 네트워크의 개수를 계산하며, 각 컴퓨터가 어떤 네트워크에 속하는지 확인하는 과정을 통해 문제를 해결합니다.

감사합니다!
