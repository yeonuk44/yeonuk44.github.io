---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Dividing_Grid_Into_Two
title: Dividing the grid into two (with.Java)
# title: Dividing the grid into two (with.Java)
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
date: 2024-08-11 09:00:00 +0900
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

## This is an article about the problem of dividing the electrical grid into two (with.Java).

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

N transmission towers are connected in the form of a tree through wires.

You want to break one of these wires and split the current grid network into two.

At this time, we want to match the number of transmission towers that the two power grids have as close as possible.

The number of transmission towers n, and wire information wires are given as parameters.

Complete the solution function to return the difference (absolute value) between the number of transmission towers held by the two grids when one of the wires is cut off and divided into two grids so that the number of transmission towers is as similar as possible.

#### Restrictions

- n is a natural number greater than 2 and less than 100.
- wires is an integer two-dimensional array with length n-1.
- Each element of wires consists of two natural numbers [v1, v2], which means that the -v1 and v2 transmission towers of the grid are wired.
- 1 ≤ v1 < v2 ≤ n.
- If the power grid network is not in the form of a tree, it is not given as an input.

#### Input/Output Examples

| n   | wires                                             | result |
| --- | ------------------------------------------------- | ------ |
| 9   | [[1,3],[2,3],[3,4],[4,5],[4,6],[4,7],[7,8],[7,9]] | 3      |
| 4   | [[1,2],[2,3],[3,4]]                               | 0      |
| 7   | [[1,2],[2,7],[3,7],[3,4],[4,5],[6,7]]             | 1      |

### my solution to the problem

```java
import java.util.ArrayList;

class Solution {
    static int cnt;
    static ArrayList<Integer>[] graph;
    static boolean[] visited;

    public int solution(int n, int[][] wires) {
        int answer = Integer.MAX_VALUE;
        int len = wires.length;

        for(int i = 0; i < len; i++){
            graph = new ArrayList[n + 1];

            for(int p = 0; p < (n + 1); p++){
                graph[p] = new ArrayList<>();
            }

            int temp = 0;

            for(int j = 0; j < len; j++){
                if(j == i) continue;
                int key = wires[j][0];
                int value = wires[j][1];
                graph[key].add(value);
                graph[value].add(key);
                temp = key;
            }

            cnt = 1;
            visited = new boolean[n + 1];
            dfs(temp);

            answer = Math.min(answer, Math.abs(2 * cnt - n));
        }
        return answer;
    }

    public static void dfs(int tempKey){
        visited[tempKey] = true;
        for(int i = 0; i < graph[tempKey].size(); i++){
            int tempValue = graph[tempKey].get(i);
            if(visited[tempValue]) continue;
            cnt++;
            dfs(tempValue);
        }
    }
}
```

### Solution Description

- n: Number of transmission towers in the grid
- wires: a two-dimensional array representing the electrical grid
- answer: a variable that stores the result value to be finally returned
- It controls the flow of the entire code and calculates the difference in the number of transmission towers by breaking the power grid one by one.
- Create a two-dimensional graph by breaking wires one by one
- graph: Two-dimensional ArrayList arrangement that indicates the connection status between transmission towers
- We generate a two-dimensional graph that ignores the corresponding wires by breaking the power grid one by one.
- Counting the number of transmission towers through DFS navigation
- Counts the number of transmission towers through the dfs method.
- DFS searches for connected transmission towers based on the transmission tower to check whether they are visiting and count the number of transmission towers.
- This calculates the number of transmission towers in the entire power grid.
- Calculate the difference between the transmission towers of the two electrical grids
- To find a value that minimizes the difference in the number of transmission towers in each power grid, compare the number of transmission towers calculated in each power grid through iterations and update the minimum value.
- Return Final Results
- Returns the minimum value of the difference in the number of transmission towers calculated by cutting all power grids one by one.

### Conclusion

In this way, the code calculates the number of transmission towers by breaking the entire power grid one by one to solve the given problem, and finds a value that minimizes the difference in the number of transmission towers between the two power grids.
