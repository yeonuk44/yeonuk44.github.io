---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Character_Coordinates
title: Creating maximum value 2 (with.Java)
# title: Creating maximum value 2 (with.Java)
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
date: 2024-04-30 09:00:00 +0900
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

## "캐릭터의 좌표(with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 RPG게임을 하고 있습니다.

게임에는 up, down, left, right 방향키가 있으며 각 키를 누르면 위, 아래, 왼쪽, 오른쪽으로 한 칸씩 이동합니다.

예를 들어 [0,0]에서 up을 누른다면 캐릭터의 좌표는 [0, 1], down을 누른다면 [0, -1], left를 누른다면 [-1, 0], right를 누른다면 [1, 0]입니다.

머쓱이가 입력한 방향키의 배열 keyinput와 맵의 크기 board이 매개변수로 주어집니다.

캐릭터는 항상 [0,0]에서 시작할 때 키 입력이 모두 끝난 뒤에 캐릭터의 좌표 [x, y]를 return하도록 solution 함수를 완성해주세요.

[0, 0]은 board의 정 중앙에 위치합니다.

예를 들어 board의 가로 크기가 9라면 캐릭터는 왼쪽으로 최대 [-4, 0]까지 오른쪽으로 최대 [4, 0]까지 이동할 수 있습니다.

#### 제한사항

- board은 [가로 크기, 세로 크기] 형태로 주어집니다.
- board의 가로 크기와 세로 크기는 홀수입니다.
- board의 크기를 벗어난 방향키 입력은 무시합니다.
- 0 ≤ keyinput의 길이 ≤ 50
- 1 ≤ board[0] ≤ 99
- 1 ≤ board[1] ≤ 99
- keyinput은 항상 up, down, left, right만 주어집니다.

#### 입출력 예시

| keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] |

<!-- | dots                                 | result |
| ------------------------------------ | ------ |
| [[1, 1], [2, 1], [2, 2], [1, 2]]     | 1      |
| [[-1, -1], [1, 1], [1, -1], [-1, 1]] | 4      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int[] solution(String[] keyinput, int[] board) {
        int[] answer = new int[2];
        int maxX = board[0] / 2;
        int maxY = board[1] / 2;

        for (String direction : keyinput) {
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

### 풀이 설명

- 좌표 이동: 주어진 방향 배열을 순회하며 각 방향에 따른 좌표 이동을 수행합니다.
- 좌표 이동 제한: 주어진 보드의 중심을 기준으로 최대 이동 가능한 범위를 설정합니다. 이동할 때 범위를 벗어나지 않도록 조건을 설정하여 좌표 이동을 제한합니다.
- 결과 반환: 최종적으로 이동한 좌표를 결과로 반환합니다.

**코드 장점**

- 유연한 방향 입력 처리: 주어진 방향에 따라 유연하게 좌표를 이동할 수 있도록 switch 문을 활용하여 각 방향에 대한 처리를 구현했습니다.
- 좌표 이동 제한 설정: 보드의 중심을 기준으로 최대 이동 가능한 범위를 설정하여 좌표 이동을 제한하였습니다.

**코드 단점**

- 이동 가능한 범위 제한만 고려: 보드의 크기가 변하는 경우나 다양한 이동 제약 조건을 고려하지 않았으므로, 특정 상황에서의 오류 가능성이 있을 수 있습니다.
