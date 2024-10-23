---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Network
title: Network (with.Java)
# title: Network (with.Java)
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
date: 2024-10-22 09:00:00 +0900
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

## I learned about the network (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

A network is a form of connection that allows information to be exchanged between computers.

For example, when computer A and computer B are directly connected, and computer B and computer C are directly connected, computer A and computer C can also be indirectly connected to exchange information.

So computers A, B, C are all on the same network.

Write a solution function to return the number of networks, given the number n of computers, 2D array computers containing information about the connection, as parameters.

#### Restrictions

- The number of computers n is a natural number greater than 1 and less than 200.
- Each computer is represented by an integer from 0 to n-1.
- If computer i and computer j are connected, represent computers[i][j] as 1.
- computer[i][i] is always 1.

<!-- #### input/output example

| n   | s   | result |
| --- | --- | ------ |
| 2   | 9   | [4, 5] |
| 2   | 1   | [-1]   |
| 2   | 8   | [4, 4] |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### problem solving

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

#### Solution Description

This code solves the problem of finding the number of networks.

Calculate the number of interconnected networks using the given n computers and two-dimensional array computers of n x n size.

For this, we use a depth-first search (DFS) algorithm.

First, declare a visited array to ensure that each computer is visited. The array is set to n in size, and all initial values are filled with false.

This indicates that not all computers were initially visited.

Then, it sequentially navigates n computers, increasing the number of networks each time it finds an unvisited computer, and performing DFS with that computer as a starting point.

DFS function dfs recursively visits other computers connected to the current index idx after it visits and processes the current index idx.

DFS currently visits and processes all computers associated with computer idx.

Recursively invokes DFS only if the computers[idx][i] value is 1, and the i-th computer is not visited.

This ties all connected computers together into one network.

This process allows you to visit all computers, increasing your answer each time you discover a new network.

Finally, after browsing all the computers, it returns the answer value to output the number of networks.

The code efficiently calculates the number of networks using the DFS algorithm and solves the problem by identifying which network each computer belongs to.

Thank you!
