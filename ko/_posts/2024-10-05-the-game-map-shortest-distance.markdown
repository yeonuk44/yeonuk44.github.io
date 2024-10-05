---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Game_Map_Shortest_Distance
title: 게임 맵 최단거리(with.Java)
# title: game map shortest distance (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, bfs]
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

ROR 게임은 두 팀으로 나누어서 진행하며, 상대 팀 진영을 먼저 파괴하면 이기는 게임입니다.

따라서, 각 팀은 상대 팀 진영에 최대한 빨리 도착하는 것이 유리합니다.

지금부터 당신은 한 팀의 팀원이 되어 게임을 진행하려고 합니다.

다음은 5 x 5 크기의 맵에, 당신의 캐릭터가 (행: 1, 열: 1) 위치에 있고, 상대 팀 진영은 (행: 5, 열: 5) 위치에 있는 경우의 예시입니다.

위 그림에서 검은색 부분은 벽으로 막혀있어 갈 수 없는 길이며, 흰색 부분은 갈 수 있는 길입니다.

캐릭터가 움직일 때는 동, 서, 남, 북 방향으로 한 칸씩 이동하며, 게임 맵을 벗어난 길은 갈 수 없습니다.

첫 번째 방법은 11개의 칸을 지나서 상대 팀 진영에 도착했습니다.

두 번째 방법은 15개의 칸을 지나서 상대팀 진영에 도착했습니다.

위 예시에서는 첫 번째 방법보다 더 빠르게 상대팀 진영에 도착하는 방법은 없으므로, 이 방법이 상대 팀 진영으로 가는 가장 빠른 방법입니다.

만약, 상대 팀이 자신의 팀 진영 주위에 벽을 세워두었다면 상대 팀 진영에 도착하지 못할 수도 있습니다.

예를 들어, 다음과 같은 경우에 당신의 캐릭터는 상대 팀 진영에 도착할 수 없습니다.

게임 맵의 상태 maps가 매개변수로 주어질 때, 캐릭터가 상대 팀 진영에 도착하기 위해서 지나가야 하는 칸의 개수의 최솟값을 return 하도록 solution 함수를 완성해주세요.

단, 상대 팀 진영에 도착할 수 없을 때는 -1을 return 해주세요.

#### 제한사항

- maps는 n x m 크기의 게임 맵의 상태가 들어있는 2차원 배열로, n과 m은 각각 1 이상 100 이하의 자연수입니다.
- n과 m은 서로 같을 수도, 다를 수도 있지만, n과 m이 모두 1인 경우는 입력으로 주어지지 않습니다.
- maps는 0과 1로만 이루어져 있으며, 0은 벽이 있는 자리, 1은 벽이 없는 자리를 나타냅니다.
- 처음에 캐릭터는 게임 맵의 좌측 상단인 (1, 1) 위치에 있으며, 상대방 진영은 게임 맵의 우측 하단인 (n, m) 위치에 있습니다.

#### 입출력 예

| maps                                                          | answer  |
| ------------------------------------------------------------- | ------- | ------ | ------ |
| [[1,0,1,1,1],[1,0,1,0,1],[1,0,1,1,1],[1,1,1,0,1],[0,0,0,0,1]] | 11      |
| [[1,0,1,1,1],[1,0,1,0,1],[1,0,1,1,1],[1,1,1,0,0],[0,0,0,0,1]] | -1      |
| <!--                                                          | numbers | target | return |
| ---------------                                               | ------  | ------ |
| [1, 1, 1, 1, 1]                                               | 3       | 5      |
| [4, 1, 2, 1]                                                  | 4       | 2      | -->    |

### 문제 풀이

```java
import java.util.Queue;
import java.util.LinkedList;

class Solution {
    public static int n, m;
    public static int answer = -1;

    public static int[] dx = {-1, 1, 0, 0};
    public static int[] dy = {0, 0, -1, 1};
    public static boolean[][] visited;

    public int solution(int[][] maps) {
        n = maps.length;
        m = maps[0].length;
        visited = new boolean[n][m];

        return bfs(0, 0, maps);
    }

    public int bfs(int x, int y, int[][] maps){
        Queue<int[]> que = new LinkedList<>();

        que.offer(new int[]{x, y, 1});
        visited[0][0] = true;

        while (!que.isEmpty()) {
            int temp[] = que.poll();
            x = temp[0];
            y = temp[1];
            int count = temp[2];

            if (x == n - 1 && y == m - 1) {
                answer = count;
                break;
            }

            for (int i = 0; i < 4; i++) {
                int nx = x + dx[i];
                int ny = y + dy[i];

                if(nx < 0 || nx >= n || ny < 0 || ny >= m) continue;
                if(maps[nx][ny] == 0) continue;
                if(!visited[nx][ny] && maps[nx][ny] == 1) {
                    visited[nx][ny] = true;
                    que.offer(new int[]{nx, ny, count + 1});
                }
            }
        }

        return answer;
    }
}
```

#### 풀이 설명

이 코드는 2차원 배열 형태의 지도에서 (0, 0) 위치에서 시작하여 (n-1, m-1) 위치로 이동하는 최단 경로를 찾는 문제를 해결하는 자바 코드입니다.

이 문제는 BFS(너비 우선 탐색)를 사용하여 해결할 수 있습니다.

각 단계에서 가능한 모든 경로를 탐색하면서 최단 경로를 찾습니다. 다음은 코드 해설입니다.

n과 m은 지도 배열의 행과 열의 크기를 나타냅니다.

answer는 최종적으로 반환할 최단 경로의 길이를 저장합니다.

초기값은 -1로 설정되어 있습니다.

dx와 dy 배열은 상하좌우 이동을 위한 방향 벡터를 나타냅니다.

visited는 특정 위치를 방문했는지 여부를 저장하는 2차원 boolean 배열입니다.

solution 메서드는 지도 배열 maps를 입력으로 받아 최단 경로의 길이를 반환합니다.

n과 m을 지도 배열의 크기로 설정하고, visited 배열을 초기화합니다.

bfs 메서드를 호출하여 (0, 0)에서 시작하는 BFS 탐색을 수행합니다.

bfs 메서드는 BFS 알고리즘을 사용하여 최단 경로를 찾습니다.

Queue를 사용하여 BFS를 구현하며, 큐에는 현재 위치와 현재까지의 이동 횟수를 저장합니다.

시작 위치 (0, 0)를 큐에 추가하고 방문 여부를 true로 설정합니다.

큐가 빌 때까지 반복하며, 큐에서 위치를 하나씩 꺼내어 현재 위치와 이동 횟수를 가져옵니다.

현재 위치가 목표 위치 (n-1, m-1)인 경우, answer를 현재 이동 횟수로 설정하고 탐색을 종료합니다.

상하좌우 네 방향으로 이동 가능한 모든 위치를 확인합니다.

지도 범위를 벗어나거나 벽(0)인 경우를 제외하고, 방문하지 않은 길(1)인 경우에만 큐에 추가하고 방문 여부를 true로 설정합니다.

최종적으로 answer를 반환합니다.

#### 결론

BFS를 사용하여 주어진 지도에서 최단 경로를 효율적으로 찾습니다.

BFS는 모든 경로를 동일한 깊이로 탐색하므로 최단 경로를 찾는 데 적합한 알고리즘입니다.
