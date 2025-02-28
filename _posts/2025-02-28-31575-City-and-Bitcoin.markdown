---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-31575-City-and-Bitcoin
title: Baekjun 31575, City and Bitcoin
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

## This is an article about Baekjun No. 14298, Vote (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

One morning, when Bitcoin's market price rose by 1 million won compared to the previous day, Jinwoo goes to the exchange and tries to sell Bitcoin.

Jinwoo should go to the exchange as soon as possible because Bitcoin's current market price is falling.

The city was formed in a grid of N by M.

Jinwoo is at the northwest end and the exchange is at the southeast end.

Some parts of the city are open spaces or roads, so Jinwoo can pass by, but some areas have buildings, so Jinwoo can't go.

If each cell is 1, it means the cell where Jinwoo can go, and if it is 0, it means the cell where Jinwoo cannot go.

The upper-left and lower-right end columns are both 1.

#### Output

On the first line, if Jinwoo can go to the exchange, he will output Yes, otherwise No.

### problem solving

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

#### Solution Description

This code uses depth-first navigation (DFS) to determine** whether a **M × N board can reach the (0,0) to (M-1, N-1) position.

First, use 'BufferedReader' to receive 'M' (number of rows) and 'N' (number of columns).

After that, create a 'board' array of 'M × N' size and receive the board information.

If the value of 'board[i][j]' is 1, it is considered a movable obstacle, and if it is 0, it is considered a non-movable obstacle.

Also, record your visit using the 'visited' array.

Define the 'dfs' function to perform the DFS navigation.

This function recursively explores whether it can reach (M-1, N-1) from the current coordinate '(dx, dy)'.

1. If '(dx, dy)' reaches the destination point '(M-1, N-1), return 'true' to end the search.
2. Returns 'false' if the current location is out of range of the board, has already been visited, or cannot be moved (if the value is zero).
3. After marking the current location as visited, perform DFS by moving to the right ('dx, dy + 1') and down ('dx + 1, dy').
4. Return 'true' if any of the routes you have traveled can reach the point of arrival.
5. Return 'false' if you cannot reach after exploring all routes.

In the 'main' function, output 'Yes' if the execution result of 'dfs' is 'true', and 'No' if 'false'.

The time complexity of this algorithm is at its worst **O(M × N)** and is being optimized using a 'visited' array to avoid revisiting the visited locations.
