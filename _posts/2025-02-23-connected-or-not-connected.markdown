---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-connected-or-not-connected
title: Baekjun 5237, Connected or Not Connected (with.Java)
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

## This is an article about Baekjun 5237 Connected or Not Connected (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Sam and Quorra are trying to build a secret base map of the Grid world that includes multiple (virtual) sites interconnected by (virtual) paths.

They know the number of sites (n), but they lack knowledge of interconnections between sites.

Several other programs within the base can provide information about connections between sites, which Sam and Quorra need to put together.

In particular, they want to make sure that they have enough information to know how to go from every site to every other site.

Your goal is to help you determine whether the specified set of connections is sufficient to secure a route from all sites to other sites.

Suppose the connection is two-way.

In other words, if you know that there is a connection between Site 1 and Site 2, you can go from Site 1 to Site 2, or vice versa.

#### Input

The first line of the test data file contains the number of test cases (≤50).

After that, each line contains a test case.

The first number of each test case is the number of sites, n (≤100).

Sites are numbered from 0 to n-1.

The second number is the number of connections between sites, k(≤200).

After that, there are k pairs of numbers, one for each connection. The connection may be repeated, and furthermore, there may be its own connection (i.e., connection from the site to itself).

#### Output

For each test case, make sure that there is a route from all sites to other sites, and output "Connected" or "Unconnected" accordingly.

### Problem Solving

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

#### Solution Description

This code is a program that verifies that all nodes are connected to each other in a given undirected graph.

First, use the Buffered Reader to quickly read the input and receive the number of test cases T as the first input.

Subsequently, the number of nodes N and the number of edges K are entered for each test case.

Graphs are represented in an adjacency list method, and after creating a list to store connection information for each node by declaring List<Integer>[] graph = new ArrayList[N];, initialize the list by the number of nodes using the for statement.

After that, K edge information is read and the corresponding node pairs are added to each other to form a undirected graph.

When the graph is complete, it uses depth-first navigation (DFS) to navigate all nodes.

Declare a boolean array visited to see if it is visited, and call the function dfs(0, graph, visited) to start the search from node 0.

The DFS function visits and processes the current node, then checks the neighboring nodes, and continues the search with a recursive call if not.

After the search, check the visited array, and if there is at least one false node, it determines that all nodes are not connected and outputs that they are not connected, and outputs that all nodes are connected if they are visited.

Finally, we optimize performance by outputting the results at once using StringBuilder.
