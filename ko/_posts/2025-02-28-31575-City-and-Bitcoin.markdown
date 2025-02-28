---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-31575-City-and-Bitcoin
title: 백준 31575번, 도시와 비트코인
# title: Baekjun 31575, City and Bitcoin
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
date: 2025-02-28 09:00:00 +0900
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

## 백준 14298번, Vote (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

전날에 비해 비트코인의 시세가 백만원이나 오른 어느 아침, 진우는 거래소에 가서 비트코인을 매도하려고 한다.

현재 비트코인의 시세가 점점 떨어지고 있기 때문에 진우는 최대한 빨리 거래소에 가야 한다.

도시는 가로 N, 세로 M 크기의 격자 모양으로 이루어졌다.

진우는 북서쪽 끝에 있고 거래소는 남동쪽 끝에 있다.

도시의 일부 구역은 공터 또는 도로라서 진우가 지나갈 수 있지만, 어떤 구역은 건물이 있어서 진우가 갈 수 없다.

각 칸이 1인 경우 진우가 갈 수 있는 칸을 의미하고 0인 경우 진우가 갈 수 없는 칸을 의미한다.

왼쪽 위의 끝 칸과 오른쪽 아래의 끝 칸은 모두 1이다.

#### 출력

첫 번째 줄에 진우가 거래소로 갈 수 있으면 Yes를, 그렇지 않으면 No를 출력한다.

### 문제 풀이

```java
import java.io.*;
import java.util.*;

class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());
        int N = Integer.parseInt(st.nextToken());
        int M = Integer.parseInt(st.nextToken());
        int[][] board = new int[M][N];
        boolean[][] visited = new boolean[M][N];

        for(int i = 0; i < M; i++){
            st = new StringTokenizer(br.readLine());
            for(int j = 0; j < N; j++){
                board[i][j] = Integer.parseInt(st.nextToken());
            }
        }

        boolean flag = dfs(board, visited, 0, 0, M, N);

        if(flag){
            System.out.println("Yes");
        }else{
            System.out.println("No");
        }
    }

    private static Boolean dfs(int[][] board, boolean[][] visited, int dx, int dy, int M, int N){
        if(dx == M - 1 && dy == N - 1){
            return true;
        }

        if(dx < 0 || dx >= M || dy < 0 || dy >= N || visited[dx][dy] || board[dx][dy] == 0){
            return false;
        }
        visited[dx][dy] = true;

        if(dfs(board, visited, dx + 1, dy, M, N)){
            return true;
        }

        if(dfs(board, visited, dx, dy + 1, M, N)){
            return true;
        }

        return false;
    }
}
```

#### 풀이 설명

이 코드는 DFS(깊이 우선 탐색)를 활용하여 **M × N 크기의 보드에서 (0,0) 위치에서 (M-1, N-1) 위치까지 도달할 수 있는지**를 판별하는 프로그램입니다.

먼저, `BufferedReader`를 사용하여 `M`(행 개수)과 `N`(열 개수)을 입력받습니다.

이후 `M × N` 크기의 `board` 배열을 생성하고, 해당 보드 정보를 입력받습니다.

`board[i][j]`의 값이 1이면 이동할 수 있고, 0이면 이동할 수 없는 장애물로 간주됩니다.

또한, `visited` 배열을 사용하여 방문 여부를 기록합니다.

DFS 탐색을 수행하기 위해 `dfs` 함수를 정의합니다.

이 함수는 현재 좌표 `(dx, dy)`에서 (M-1, N-1)까지 도달할 수 있는지를 재귀적으로 탐색합니다.

1. 만약 `(dx, dy)`가 도착 지점 `(M-1, N-1)`에 도달하면 `true`를 반환하여 탐색을 종료합니다.
2. 현재 위치가 보드 범위를 벗어나거나, 이미 방문한 위치이거나, 이동할 수 없는 위치(값이 0인 경우)이면 `false`를 반환합니다.
3. 현재 위치를 방문한 것으로 표시한 후, 오른쪽(`dx, dy + 1`)과 아래쪽(`dx + 1, dy`) 방향으로 이동하며 DFS를 수행합니다.
4. 만약 이동한 경로 중 하나라도 도착 지점까지 도달할 수 있다면 `true`를 반환합니다.
5. 모든 경로를 탐색한 후에도 도착할 수 없다면 `false`를 반환합니다.

`main` 함수에서 `dfs` 실행 결과가 `true`이면 `"Yes"`, `false`이면 `"No"`를 출력합니다.

이 알고리즘의 시간 복잡도는 최악의 경우 **O(M × N)**이며, 방문한 위치를 다시 탐색하지 않도록 `visited` 배열을 사용하여 최적화하고 있습니다.
