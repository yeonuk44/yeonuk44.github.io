---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Vowel_Dictionary
title: Vowel dictionary (with.Java)
# title: Vowel dictionary (with.Java)
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
date: 2024-08-12 09:00:00 +0900
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

## 모음 사전 (with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

사전에 알파벳 모음 'A', 'E', 'I', 'O', 'U'만을 사용하여 만들 수 있는, 길이 5 이하의 모든 단어가 수록되어 있습니다. 사전에서 첫 번째 단어는 "A"이고, 그다음은 "AA"이며, 마지막 단어는 "UUUUU"입니다.

단어 하나 word가 매개변수로 주어질 때, 이 단어가 사전에서 몇 번째 단어인지 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- n은 2 이상 100 이하인 자연수입니다.
- wires는 길이가 n-1인 정수형 2차원 배열입니다.
- wires의 각 원소는 [v1, v2] 2개의 자연수로 이루어져 있으며, 이는 전력망의 - v1번 송전탑과 v2번 송전탑이 전선으로 연결되어 있다는 것을 의미합니다.
- 1 ≤ v1 < v2 ≤ n 입니다.
- 전력망 네트워크가 하나의 트리 형태가 아닌 경우는 입력으로 주어지지 않습니다.

#### 입출력 예시

| n   | wires                                             | result |
| --- | ------------------------------------------------- | ------ |
| 9   | [[1,3],[2,3],[3,4],[4,5],[4,6],[4,7],[7,8],[7,9]] | 3      |
| 4   | [[1,2],[2,3],[3,4]]                               | 0      |
| 7   | [[1,2],[2,7],[3,7],[3,4],[4,5],[6,7]]             | 1      |

### 문제에 대한 나의 풀이

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

### 풀이 설명

- n: 전력망에 있는 송전탑의 개수
- wires: 전력망을 나타내는 2차원 배열
- answer: 최종적으로 반환할 결과값을 저장하는 변수
- 전체 코드의 흐름을 제어하고, 전력망을 하나씩 끊어가며 송전탑의 개수 차이를 계산합니다.
- 전선을 하나씩 끊으며 2차원 그래프 생성
- graph: 송전탑 간의 연결 상태를 나타내는 2차원 ArrayList 배열
- 전력망을 하나씩 끊어가며 해당 전선을 무시한 2차원 그래프를 생성합니다.
- DFS 탐색을 통한 송전탑 개수 카운팅
- dfs 메서드를 통해 송전탑 개수를 카운트합니다.
- 해당 송전탑을 기준으로 연결된 송전탑들을 DFS 탐색하면서 방문 여부를 체크하고 송전탑 개수를 셉니다.
- 이를 통해 전체 전력망의 송전탑 개수를 구합니다.
- 두 전력망의 송전탑 차이 계산
- 각 전력망의 송전탑 개수 차이가 최소가 되는 값을 찾기 위해 반복문을 통해 각각의 전력망에서 계산된 송전탑 개수를 비교하고 최솟값을 업데이트합니다.
- 최종 결과 반환
- 모든 전력망을 하나씩 끊어가며 계산한 송전탑 개수 차이 중에서 최솟값을 반환합니다.

### 결론

이렇게 코드는 주어진 문제를 해결하기 위해 전체 전력망을 하나씩 끊어가며 송전탑의 개수를 계산하고, 두 전력망의 송전탑 개수 차이가 최소가 되는 값을 찾습니다.
