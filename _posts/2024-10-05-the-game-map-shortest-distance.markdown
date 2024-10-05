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

## This is an article about the shortest distance (with.Java) of the game map.

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

The ROR game is divided into two teams, and if you destroy the opposing team's camp first, you win.

Therefore, it is advantageous for each team to arrive at the opposing team's camp as soon as possible.

From now on, you are going to be a team member and proceed with the game.

Here is an example of a 5 x 5 map where your character is in the (row: 1, column: 1) position, and the opposing team camp is in the (row: 5, column: 5) position.

In the picture above, the black part is blocked by a wall, so you can't go, and the white part is the way to go.

When the character moves, it moves one space in the east, west, south, and north directions, and the path outside the game map cannot be taken.

The first method went past 11 compartments and reached the opposing team's camp.

The second method went past 15 compartments and reached the opposing team's camp.

In the above example, there is no faster way to reach the opposing team's camp than the first, so this is the quickest way to get to the opposing team's camp.

If the opposing team has a wall built around their own team's camp, they may not be able to reach the opposing team's camp.

For example, your character cannot reach the opposing team camp in the following cases.

When the status maps of the game map are given as parameters, complete the solution function to return the minimum number of spaces a character must pass to reach the opposing team's camp.

However, if you can't reach the other team's camp, please return -1.

#### Restrictions

- Maps is a two-dimensional array containing the status of an n x m - sized game map, where n and m are natural numbers greater than 1 and less than 100 respectively.
- N and m can be the same or different, but if both n and m are 1, they are not given as input.
- The maps are made up of only 0 and 1, where 0 represents where the wall is and 1 represents where the wall is not.
- Initially, the character is in the upper left corner of the game map, in the upper left corner of the game map, and the other side is in the lower right corner of the game map, in the lower right corner of the game map, in the (n, m).

#### Input/output Examples

| maps                                                          | answer  |
| ------------------------------------------------------------- | ------- | ------ | ------ |
| [[1,0,1,1,1],[1,0,1,0,1],[1,0,1,1,1],[1,1,1,0,1],[0,0,0,0,1]] | 11      |
| [[1,0,1,1,1],[1,0,1,0,1],[1,0,1,1,1],[1,1,1,0,0],[0,0,0,0,1]] | -1      |
| <!--                                                          | numbers | target | return |
| ---------------                                               | ------  | ------ |
| [1, 1, 1, 1, 1]                                               | 3       | 5      |
| [4, 1, 2, 1]                                                  | 4       | 2      | -->    |

### problem solving

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

#### Solution Description

This code is a Java code that solves the problem of finding the shortest path on a map in the form of a two-dimensional array starting at the (0, 0) position and going to the (n-1, m-1) position.

This problem can be resolved by using BFS (width priority navigation).

Find the shortest path as you navigate through all possible paths at each stage. This is the code description.

n and m represent the sizes of rows and columns in a map array.

answer stores the length of the shortest path to return eventually.

The initial value is set to -1.

The dx and dy arrays represent directional vectors for up, down, left, and right movements.

A visited is a two-dimensional boolean array that stores whether a particular location has been visited.

The solution method takes the map array maps as input and returns the length of the shortest path.

Set n and m to the size of the map array, and initialize the visited array.

Call the bfs method to perform a BFS discovery starting at (0, 0).

The bfs method uses the BFS algorithm to find the shortest path.

Use queues to implement BFS, which stores the current location and the number of moves up to the present in the queue.

Add the start position (0, 0) to the queue and set the visit status to true.

Repeat until the queue is empty, pulling the position out of the queue one by one to get the current position and number of moves.

If the current position is the target position (n-1, m-1), set the answer to the current number of moves and end the navigation.

Check all positions that can be moved up, down, left, and right.

Add to the queue only if it is a path (1) that has not been visited, except if it is outside the map range or is a wall (0), and set whether to visit to true.

Finally, answer is returned.

#### Conclusion

Using BFS, we efficiently find the shortest path on a given map.

BFS is a suitable algorithm for finding shortest paths as it navigates all paths to the same depth.
