---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Character_Coordinates
title: Character coordinates (with.Java)
# title: Character coordinates (with.Java)
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
date: 2024-04-29 09:00:00 +0900
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

## This is an article about the "character coordinates (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

I'm playing a stupid RPG game.

There are up, down, left, and right direction keys in the game, and pressing each key moves one space up, down, left, or right.

For example, if you press up in [0,0], the character's coordinates will be [0, 1], if you press down, [0, -1], if you press left, [-1, 0], if you press right, the coordinates will be [0, 1]. 1, 0].

The array keyinput of the direction keys entered by the mage and the size of the map board are given as parameters.

When the character always starts at [0,0], please complete the solution function so that it returns the character's coordinates [x, y] after all key inputs are completed.

[0, 0] is located in the exact center of the board.

For example, if the horizontal size of the board is 9, the character can move up to [-4, 0] to the left and up to [4, 0] to the right.

#### Restrictions

- The board is given in the form of [horizontal size, vertical size].
- The horizontal and vertical sizes of the board are odd.
- Directional key input outside the size of the board is ignored.
- 0 ≤ length of keyinput ≤ 50
- 1 ≤ board[0] ≤ 99
- 1 ≤ board[1] ≤ 99
- Keyinput is always up, down, left, and right.

#### Input/Output Example

| keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] |

<!-- | dots | result |
| ------------------------------------ | ------ |
| [[1, 1], [2, 1], [2, 2], [1, 2]] | 1 |
| [[-1, -1], [1, 1], [1, -1], [-1, 1]] | 4 | -->

### My solution to the problem

```java
class Solution {
     public int[] solution(String[] keyinput, int[] board) {
         int[] answer = new int[2];
         int maxX = board[0] / 2;
         int maxY = board[1] / 2;

         for (String direction: keyinput) {
             switch (direction) {
                 case "up":
                     if (answer[1] < maxY) {
                         answer[1]++;
                     }
                     break;
                 case "down":
                     if (answer[1] > -maxY) {
                         answer[1]--;
                     }
                     break;
                 case "left":
                     if (answer[0] > -maxX) {
                         answer[0]--;
                     }
                     break;
                 case "right":
                     if (answer[0] < maxX) {
                         answer[0]++;
                     }
                     break;
                 default:
                     break;
             }
         }

         return answer;
     }
}
```

### Solution explanation

- Coordinate movement: Iterates through the given direction array and performs coordinate movement in each direction.
- Coordinate movement limit: Set the maximum range of movement based on the center of the given board. Limit coordinate movement by setting conditions to prevent movement out of range.
- Return result: Returns the final moved coordinates as a result.

**Code Advantages**

- Flexible direction input processing: Processing for each direction was implemented using a switch statement so that coordinates can be moved flexibly according to a given direction.
- Coordinate movement limit setting: Coordinate movement is limited by setting the maximum range of movement based on the center of the board.

**Code Disadvantages**

- Only considers limitations in the range of movement: Since the board size changes or various movement constraints are not considered, there may be a possibility of errors in certain situations.
