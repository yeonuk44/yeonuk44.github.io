---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-26169-eat-apples-within-three-times
title: Baekjun, 26169, let's eat apples within three times (with.Java)
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

## Baekjun No. 26169, let's eat apples within three times (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

A board measuring 5 x 5 is given. The board consists of a square grid measuring 1 x 1.

The grid of the board is divided into a grid with one apple, a grid with obstacles, and a grid with blanks.

The locations of the grids are denoted by (r, c). R denotes row numbers, and c denotes column numbers.

The row number has a top position of 0 and increases by 1 in the bottom direction.

The column number has a leftmost position of 0 and increases by 1 to the right.

That is, the top left position is (0, 0) and the bottom right position is (4, 4).

Currently, one student is in the (r, c) position and can move one space in one of the up, down, left, and right directions with one movement.

When a student moves to a cell with an apple, he or she eats one apple in that cell.

You can't move to a compartment with an obstacle.

The cell where the student has passed is changed to a cell with an obstacle as soon as the student leaves the cell.

In other words, as soon as the student moves one space in the upward, downward, left, and right directions from the corresponding space, the corresponding space is changed to a space with an obstacle.

If the student can eat two or more apples with no more than three moves at the current location (r, c), output 1, otherwise output 0.

#### Input

Information on the board is given across five lines from the first line.

The jth number in the i-th row represents information in the (i - 1)th row and (j - 1)th column of the board.

If the information on the board is 1, the corresponding space represents a grid with one apple, if 0 represents a grid with blanks, and if -1, it represents a grid with obstacles.

In the next line, the student's current positions r, c are given in order with blanks between them.

#### Output

In the first line, if the student can eat two or more apples with no more than three movements at the current location (r, c), output 1, and output 0 if he or she cannot eat.

#### Restrictions

0 ≤ r, c ≤ 4

The current location (r, c) is blank.

### problem solving

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

#### Solution Description

This code uses Depth Priority Exploration (DFS) to determine if a student can eat two or more apples on a 5×5 board \*\*up to three trips.

First, receive a 5×5 board and set the starting position for the student.

In this case, the board may include a blank space 0, an apple 1, and an obstacle-1.

There are four directions in which students can move: up, down, left, and right, and they are managed using the arrangement of 'dx' and 'dy'.

Track the number of moves ('moves') and the number of apples eaten while performing the DFS navigation.

If the number of moves exceeds 3, no more searching is performed, and if you eat two or more apples, the 'found' variable is 'true'
