---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Save_Zone
title: Safe zone (with.Java)
# title: Safe zone (with.Java)
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
date: 2024-05-09 09:00:00 +0900
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

## This article looks into the "safe zone (with.Java)" issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The area with the mine and the diagonal spaces above, below, left, and right adjacent to the mine are all classified as dangerous areas.

Mines are marked as 1 on a two-dimensional array board, and on the board there are only area 1 with mines buried and area 0 without mines.

When the map board of a landmine-laden area is given as a parameter, complete the solution function to return the number of safe area squares.

#### Restrictions

- board is an n x n array.
- 1 ≤ n ≤ 100
- Mines are marked with 1.
  -On the board, there is only area 1 with mines and area 0 without mines.

#### Input/Output Example

<!-- | keyinput | board | result |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1] |
| ["down", "down", "down", "down", "down"] | [7, 9] | [0, -4] | -->

| my_string                                                                                                                | result |
| ------------------------------------------------------------------------------------------------------------------------ | ------ |
| [[0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 1, 0, 0], [ 0, 0, 0, 0, 0]]                                   | 16     |
| [[0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 1, 1, 0], [ 0, 0, 0, 0, 0]]                                   | 13     |
| [[1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1]] | 0      |

### My solution to the problem

```java
class Solution {
 public int solution(int[][] board) {
 int[][] secondArr = new int[board.length+2][board.length+2];
 int answer = 0;
 for(int i = 0; i < board.length; i++){
 for(int j = 0; j < board.length; j++){
 if(board[i][j] == 1){
 for(int a = i; a <= i+2; a++){
 for(int b = j; b <= j+2; b++){
 if(secondArr[a][b] != 1){
 secondArr[a][b] = 1;
 }
 }
 }
 }
 }
 }
 for(int i = 1; i < secondArr.length - 1; i++){
 for(int j = 1; j < secondArr.length-1; j++){
 if(secondArr[i][j] == 0){
 answer++;
 }
 }
 }
 return answer;
 }
}
```

### Solution explanation

- Create a new 2-dimensional array: Create a new 2-dimensional array, secondArr, whose size is 1 larger than the existing board array. This is to handle the border portion of the board.
- Board search and surrounding cell update: When searching the existing board and finding a cell with a value of 1, all 8 surrounding cells around that cell are updated to 2.
- Searching a new array and counting the number of cells with a value of 0: Searching a new array, counting the number of cells with a value of 0 and storing them in the answer variable.
- Return result: Returns the number of cells that are finally counted as 0.

**Code pros and cons**

- Advantage: The code is concise by using an efficient method of counting zero cells. The border areas of the board can be easily handled without any additional processing.
- Disadvantage: This code processes all cells on the board by traversing them one more time, which can result in inefficient execution time. Performance may be affected, especially if the board is large.
