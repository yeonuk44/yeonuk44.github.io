---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Farigue
title: Fatigue (with.Java)
# title: Fatigue (with.Java)
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
date: 2024-08-10 09:00:00 +0900
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

## This is an article about the fatigue (with.Java) problem.

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

The XX game has a fatigue degree system (expressed in integers above zero), and you can explore dungeons using a certain fatigue degree.

At this point, each dungeon has the "minimum required fatigue" needed to start the expedition and the "consumption fatigue" consumed when the dungeon expedition is completed.

"Minimum required fatigue" refers to the minimum fatigue you need to have to explore the dungeon, and "consumption fatigue" refers to the fatigue you consume after exploring the dungeon.

For example, in order to explore dungeons with "minimum required fatigue" of 80 and "consumption fatigue" of 20, the user's current remaining fatigue must be at least 80; after exploring dungeons, the user consumes 20 fatigue.

There are several dunes in this game that you can explore once a day, and one user is trying to explore them as much as possible today.

Complete the solution function to return the maximum number of throws the user can explore, given the user's current fatigue k and the two-dimensional arrangement dungeons containing "minimum required fatigue" and "consumption fatigue" for each dungeon as parameters.

#### Restrictions

- k is a natural number greater than 1 and less than 5,000.
- The length (row) of the dungeons (i.e., the number of dungeons) is 1 or more and 8 or less.
- The distance (column) of the dungeons is 2.
- Each row of the dungeons is ["Minimum Required Fatigue", "Consumption Fatigue"] for each dungeon.
- "Minimum required fatigue" is always greater than or equal to "consumption fatigue".
- "Minimum required fatigue" and "consumption fatigue" are natural numbers greater than 1 and less than 1,000.
- The different dungeons ["Minimum Required Fatigue" and "Consumption Fatigue"] can be the same.

#### Input/Output Examples

| k   | dungeons                  | result |
| --- | ------------------------- | ------ |
| 80  | [[80,20],[50,40],[30,10]] | 3      |

### my solution to the problem

```java
class Solution {
    public int answer = 0;
    public boolean[] visit;

    public int solution(int k, int[][] dungeons) {
        visit = new boolean[dungeons.length];

        dfs(0, k, dungeons);

        return answer;
    }

    public void dfs(int depth, int k, int[][] dungeons) {
        for (int i = 0; i < dungeons.length; i++) {
            if(visit[i] || dungeons[i][0] > k){
                continue;
            } else{
                visit[i] = true;
                dfs(depth + 1, k - dungeons[i][1], dungeons);
                visit[i] = false;
            }
        }
        answer = Math.max(answer, depth);
    }
}
```

### Solution Description

[80,20], [50,40], [30,10], which is impossible because the third dungeon cannot be searched, and if the third dungeon is in the order of the least exhausting fatigue, [30,10], [80,20], [50,40] is impossible because the remaining dungeon is 70 when the first dungeon is turned.

In other words, the only way to search for the number of all cases using complete search was to solve it by DFS using a recursive function.

The dfs method is recursively called.

Each call takes as an argument the depth of the search to date, the current level (k), and the Dungeons.

Iterate to explore dungeons where the demand level is below the current level among the non-visited dungeons.

Visit the first undiscovered dungeon and recursively call the demand level of that dungeon to the value minus the current level.

When the recursive call ends, change the visit to false again.

### Conclusion

Record the maximum search depth as you navigate all dunes, and finally return it.
The code provides a simple way to explore all possible paths using the DFS algorithm and to find the maximum search depth among them.
