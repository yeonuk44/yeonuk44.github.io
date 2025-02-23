---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-connected-or-not-connected
title: 백준 5237번, Connected or Not Connected (with.Java)
# title: Baekjun 5237, Connected or Not Connected (with.Java)
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
date: 2025-02-23 09:00:00 +0900
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

## 백준 5237번 Connected or Not Connected (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

Sam과 Quorra는 (가상) 경로로 상호 연결된 여러 (가상) 사이트를 포함하는 Grid 세계의 비밀 기지 지도를 구축하려고 노력하고 있습니다.

그들은 사이트 수(n)를 알고 있지만, 사이트 간의 상호 연결에 대한 지식은 부족합니다.

기지 내에 있던 여러 다른 프로그램들은 사이트 간의 연결에 대한 정보를 제공할 수 있으며, Sam과 Quorra는 이를 종합해야 합니다.

특히, 그들은 모든 사이트에서 다른 모든 사이트로 이동하는 방법을 알 수 있는 충분한 정보를 가지고 있는지 확인하고자 합니다.

귀하의 목표는 지정된 연결 세트가 모든 사이트에서 다른 사이트로 가는 경로를 확보하기에 충분한지 여부를 결정하는 데 도움을 주는 것입니다.

연결이 양방향이라고 가정합니다.

즉, 사이트 1과 사이트 2 사이에 연결이 있다는 것을 알고 있다면 사이트 1에서 사이트 2로, 또는 그 반대로 이동할 수 있습니다.

#### 입력

테스트 데이터 파일의 첫 번째 줄에는 테스트 케이스의 수(≤ 50)가 포함되어 있습니다.

그 후 각 줄에는 테스트 케이스가 포함됩니다.

각 테스트 케이스의 첫 번째 숫자는 사이트의 수, n(≤ 100)입니다.

사이트는 0에서 n - 1까지 번호가 매겨집니다.

두 번째 숫자는 사이트 간의 연결 수, k(≤ 200)입니다.

그 후 각 연결마다 하나씩 k쌍의 숫자가 있습니다. 연결이 반복될 수 있으며, 더 나아가 자체 연결 (즉, 사이트에서 자체로의 연결)이 있을 수 있습니다.

#### 출력

각 테스트 케이스마다 모든 사이트에서 다른 사이트로 가는 경로가 있는지 확인하고, 이에 따라 "연결됨" 또는 "연결되지 않음"을 출력해야 합니다.

### 문제 풀이

```java
import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int T = Integer.parseInt(br.readLine());
        StringBuilder sb = new StringBuilder();

        for (int i = 0; i < T; i++){
            StringTokenizer st = new StringTokenizer(br.readLine());
            int N = Integer.parseInt(st.nextToken());
            int K = Integer.parseInt(st.nextToken());

            List<Integer>[] graph = new ArrayList[N];
            for(int j = 0; j < N; j++){
                graph[j] = new ArrayList<>();
            }

            for(int j = 0; j < K; j++){
                int u = Integer.parseInt(st.nextToken());
                int v = Integer.parseInt(st.nextToken());
                graph[u].add(v);
                graph[v].add(u);
            }

            boolean[] visited = new boolean[N];
            dfs(0, graph, visited);

            boolean isConnected = true;
            for(int j = 0; j < N; j++){
                if(!visited[j]){
                    isConnected = false;
                    break;
                }
            }

            sb.append(isConnected ? "Connected.\n" : "Not connected.\n");
        }

        System.out.print(sb);
    }

    private static void dfs(int node, List<Integer>[] graph, boolean[] visited){
        visited[node] = true;
        for(int next : graph[node]){
            if(!visited[next]){
                dfs(next, graph, visited);
            }
        }
    }
}
```

#### 풀이 설명

이 코드는 주어진 무방향 그래프에서 모든 노드가 서로 연결되어 있는지를 확인하는 프로그램입니다.

먼저, BufferedReader를 사용하여 입력을 빠르게 읽어오며 첫 번째 입력값으로 테스트 케이스 개수 T를 받습니다.

이후, 각 테스트 케이스마다 노드 개수 N과 간선 개수 K를 입력받습니다.

그래프는 인접 리스트 방식으로 표현되며, List<Integer>[] graph = new ArrayList[N]; 를 선언하여 각 노드에 대한 연결 정보를 저장할 리스트를 생성한 후 for 문을 이용해 노드 개수만큼 리스트를 초기화합니다.

이후 K개의 간선 정보를 읽어와 해당 노드 쌍을 서로 추가하여 무방향 그래프를 형성합니다.

그래프가 완성되면 DFS(깊이 우선 탐색)를 이용해 모든 노드를 탐색합니다.

방문 여부를 확인하기 위해 boolean 배열 visited를 선언하고, dfs(0, graph, visited) 함수를 호출하여 0번 노드부터 탐색을 시작합니다.

DFS 함수는 현재 노드를 방문 처리한 후 인접한 노드들을 확인하며 방문하지 않은 경우 재귀 호출을 통해 탐색을 계속 진행합니다.

탐색이 끝난 후 visited 배열을 확인하며, 하나라도 false인 노드가 있으면 모든 노드가 연결되지 않은 것으로 판단하여 연결되지 않음을 출력하고, 모든 노드가 방문되었다면 연결됨을 출력합니다.

마지막으로 StringBuilder를 사용하여 결과를 한 번에 출력함으로써 성능을 최적화합니다.
