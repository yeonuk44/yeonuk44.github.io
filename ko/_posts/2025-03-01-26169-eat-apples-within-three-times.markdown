---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-26169-eat-apples-within-three-times
title: 백준 26169번, 세 번 이내에 사과를 먹자 (with.Java)
# title: Baekjun, 26169, let's eat apples within three times
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
date: 2025-03-01 09:00:00 +0900
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

## 백준 26169번, 세 번 이내에 사과를 먹자 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

5 x 5 크기의 보드가 주어진다. 보드는 1 x 1 크기의 정사각형 격자로 이루어져 있다.

보드의 격자는 사과가 1개 있는 격자, 장애물이 있는 격자, 빈칸으로 되어 있는 격자로 구분된다.

격자의 위치는 (r, c)로 표시한다. r은 행 번호, c는 열 번호를 나타낸다.

행 번호는 맨 위 위치가 0이고 아래 방향으로 1씩 증가한다.

열 번호는 맨 왼쪽 위치가 0이고 오른쪽으로 1씩 증가한다.

즉, 맨 왼쪽 위 위치가 (0, 0), 맨 아래 오른쪽 위치가 (4, 4)이다.

현재 한 명의 학생이 (r, c) 위치에 있고 한 번의 이동으로 상, 하, 좌, 우 방향 중에서 한가지 방향으로 한 칸 이동할 수 있다.

학생이 사과가 있는 칸으로 이동하면 해당 칸에 있는 사과를 1개 먹는다.

장애물이 있는 칸으로는 이동할 수 없다.

학생이 지나간 칸은 학생이 해당 칸을 떠나는 즉시 장애물이 있는 칸으로 변경된다.

즉, 학생이 해당 칸에서 상, 하, 좌, 우 방향으로 한 칸 이동하는 즉시 해당 칸은 장애물이 있는 칸으로 변경된다.

학생이 현재 위치 (r, c)에서 세 번 이하의 이동으로 사과를 2개 이상 먹을 수 있으면 1을 출력하고, 그렇지 않으면 0을 출력하자.

#### 입력

첫 번째 줄부터 다섯 개의 줄에 걸쳐 보드의 정보가 주어진다.

i번째 줄의 j번째 수는 보드의 (i - 1)번째 행, (j - 1)번째 열의 정보를 나타낸다.

보드의 정보가 1이면 해당 칸은 사과가 1개 있는 격자임을 나타내고, 0이면 빈칸이 있는 격자를 나타내고, -1이면 장애물이 있는 격자임을 나타낸다.

다음 줄에 학생의 현재 위치 r, c가 빈칸을 사이에 두고 순서대로 주어진다.

#### 출력

첫 번째 줄에 학생이 현재 위치 (r, c)에서 세 번 이하의 이동으로 사과를 2개 이상 먹을 수 있으면 1을 출력하고, 먹을 수 없으면 0을 출력한다.

#### 제한

0 ≤ r, c ≤ 4

현재 위치 (r, c)는 빈칸이다.

### 문제 풀이

```java
import java.io.*;
import java.util.*;

class Main {
    static int[][] board = new int[5][5];
    static int[] dx = {-1, 1, 0, 0};
    static int[] dy = {0, 0, -1, 1};
    static boolean found = false;

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st;

        for (int i = 0; i < 5; i++) {
            st = new StringTokenizer(br.readLine());
            for (int j = 0; j < 5; j++) {
                board[i][j] = Integer.parseInt(st.nextToken());
            }
        }

        st = new StringTokenizer(br.readLine());
        int startX = Integer.parseInt(st.nextToken());
        int startY = Integer.parseInt(st.nextToken());

        dfs(startX, startY, 0, 0);

        System.out.println(found ? 1 : 0);
    }

    static void dfs(int x, int y, int moves, int apples) {
        if (moves > 3) return;

        if (apples >= 2) {
            found = true;
            return;
        }

        int temp = board[x][y];
        board[x][y] = -1;

        for (int i = 0; i < 4; i++) {
            int nx = x + dx[i];
            int ny = y + dy[i];

            if (nx < 0 || nx >= 5 || ny < 0 || ny >= 5 || board[nx][ny] == -1) continue;

            dfs(nx, ny, moves + 1, apples + (board[nx][ny] == 1 ? 1 : 0));

            if (found) return;
        }

        board[x][y] = temp;
    }
}
```

#### 풀이 설명

이 코드는 DFS(깊이 우선 탐색)를 이용하여 5×5 크기의 보드에서 학생이 **최대 3번 이동하면서 사과를 2개 이상 먹을 수 있는지**를 판별하는 프로그램입니다.

먼저, 5×5 크기의 보드를 입력받고, 학생이 시작하는 위치를 설정합니다.

이때, 보드에는 빈 칸(0), 사과(1), 장애물(-1)이 포함될 수 있습니다.

학생이 이동할 수 있는 방향은 상, 하, 좌, 우 네 가지이며, 이를 `dx`와 `dy` 배열을 이용해 관리합니다.

DFS 탐색을 수행하면서 이동 횟수(`moves`)와 먹은 사과 개수(`apples`)를 추적합니다.

이동 횟수가 3번을 초과하면 더 이상 탐색하지 않으며, 사과를 2개 이상 먹으면 `found` 변수를 `true`로 설정하고 탐색을 종료합니다.

각 위치를 방문할 때는 현재 위치의 값을 `-1`로 변경하여 다시 방문하지 않도록 처리합니다.

이후 네 방향으로 이동하며 DFS를 재귀적으로 호출합니다.

이동할 수 없는 경우(범위를 벗어나거나 장애물인 경우)에는 해당 방향으로 탐색하지 않습니다.

DFS 탐색이 끝난 후에는 백트래킹을 위해 원래 값으로 되돌립니다.

이렇게 하면 다른 경로도 정상적으로 탐색할 수 있습니다.

마지막으로, `found` 값에 따라 결과를 출력합니다.

사과를 2개 이상 먹을 수 있는 경로가 존재하면 `1`을, 그렇지 않으면 `0`을 출력합니다.

이 알고리즘의 시간 복잡도는 최악의 경우 **4^3 = 64**개의 경로를 탐색해야 하지만, `found` 변수를 활용하여 조기에 탐색을 종료하기 때문에 효율적으로 동작합니다.

DFS를 활용하여 가능한 모든 경로를 탐색하면서 조건을 만족하는지 판별하는 것이 이 코드의 핵심입니다.
