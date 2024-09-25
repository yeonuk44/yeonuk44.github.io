---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Stock_Price_Problem
title: Stock price (with.Java)
# title: Stock price (with.Java)
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
date: 2024-09-25 09:00:00 +0900
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

## 주식가격 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

운영체제의 역할 중 하나는 컴퓨터 시스템의 자원을 효율적으로 관리하는 것입니다.

이 문제에서는 운영체제가 다음 규칙에 따라 프로세스를 관리할 경우 특정 프로세스가 몇 번째로 실행되는지 알아내면 됩니다.

1. 실행 대기 큐(Queue)에서 대기중인 프로세스 하나를 꺼냅니다.
2. 큐에 대기중인 프로세스 중 우선순위가 더 높은 프로세스가 있다면 방금 꺼낸 프로세스를 다시 큐에 넣습니다.
3. 만약 그런 프로세스가 없다면 방금 꺼낸 프로세스를 실행합니다.
   3.1 한 번 실행한 프로세스는 다시 큐에 넣지 않고 그대로 종료됩니다.
   예를 들어 프로세스 4개 [A, B, C, D]가 순서대로 실행 대기 큐에 들어있고, 우선순위가 [2, 1, 3, 2]라면 [C, D, A, B] 순으로 실행하게 됩니다.

현재 실행 대기 큐(Queue)에 있는 프로세스의 중요도가 순서대로 담긴 배열 priorities와, 몇 번째로 실행되는지 알고싶은 프로세스의 위치를 알려주는 location이 매개변수로 주어질 때, 해당 프로세스가 몇 번째로 실행되는지 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- priorities의 길이는 1 이상 100 이하입니다.
- priorities의 원소는 1 이상 9 이하의 정수입니다.
- priorities의 원소는 우선순위를 나타내며 숫자가 클 수록 우선순위가 높습니다.
- location은 0 이상 (대기 큐에 있는 프로세스 수 - 1) 이하의 값을 가집니다.
- priorities의 가장 앞에 있으면 0, 두 번째에 있으면 1 … 과 같이 표현합니다.

#### 입출력 예

| priorities         | location | return |
| ------------------ | -------- | ------ |
| [2, 1, 3, 2]       | 2        | 1      |
| [1, 1, 9, 1, 1, 1] | 0        | 5      |

### 문제 풀이

```java
import java.util.Queue;
import java.util.LinkedList;
import java.util.Collections;
import java.util.Arrays;
class Solution {
    public int solution(int[] priorities, int location) {
        int answer = 0;
        Queue<Integer> queue = new LinkedList<>();
        int want_num = priorities[location];
        int count = 0;
        for(int i : priorities){
            queue.offer(i);
            if(want_num <= i){
                count++;
            }
        }
        if(count == 0){
            return 1;
        }
        Integer[] arr = Arrays.stream(priorities).boxed().toArray(Integer[]::new);
        Arrays.sort(arr, Collections.reverseOrder());
        int idx = 0;
        while(!queue.isEmpty()){
            int temp = 0;
            if(queue.peek() == arr[idx]){
                answer++;
                idx++;
                queue.poll();
                if(location == 0){
                    break;
                }
                location--;
            }else{
                temp = queue.poll();
                queue.offer(temp);
                location--;
                if(location < 0){
                    location = queue.size() - 1;
                }
            }
        }

        return answer;
    }
}
```

#### 풀이 설명

이 코드는 프린터의 작업 우선순위를 처리하는 문제를 해결합니다.

주어진 작업 우선순위 배열과 특정 위치의 작업이 몇 번째로 출력되는지를 계산하는 과정을 다음과 같이 구현합니다.

코드 해설

필요한 라이브러리 임포트

Queue, LinkedList, Collections, Arrays 라이브러리를 가져옵니다.

메서드 정의

solution 메서드를 정의하고, int[] priorities와 int location을 입력으로 받습니다.

변수 answer를 초기화합니다.

이는 최종적으로 반환할 값으로, 특정 작업이 몇 번째로 출력되는지를 나타냅니다.

큐 초기화

Queue<Integer> 타입의 queue를 생성합니다.

location 위치의 우선순위를 want_num 변수에 저장합니다.

priorities 배열의 각 요소를 큐에 삽입하면서, want_num보다 크거나 같은 요소의 개수를 count 변수에 저장합니다.

만약 count가 0이면, 이는 want_num이 가장 높은 우선순위임을 의미하므로 1을 반환합니다.

우선순위 배열 정렬

priorities 배열을 내림차순으로 정렬하여 arr 배열에 저장합니다. 이를 통해 가장 높은
우선순위부터 처리할 수 있습니다.

작업 순서 계산

정렬된 배열 arr의 요소와 큐의 앞 요소를 비교하면서 순서대로 처리합니다.

큐의 앞 요소가 현재 처리할 우선순위와 같으면 answer를 증가시키고, 큐에서 해당 요소를 제거합니다.

location이 0이면, 이는 우리가 찾는 작업이므로 루프를 종료합니다.

큐의 앞 요소가 현재 처리할 우선순위와 다르면 큐의 앞 요소를 뒤로 보내고, location 값을 조정합니다.

location이 0 미만이 되면 큐의 마지막으로 이동합니다.

결과 반환

answer를 반환하여 특정 작업이 몇 번째로 출력되는지를 반환합니다.

예제 입력

예를 들어, priorities가 [2, 1, 3, 2]이고 location이 2라면, 출력되는 순서는 다음과 같습니다:

3 (위치 2, 첫 번째 출력)

2 (위치 0, 두 번째 출력)

2 (위치 3, 세 번째 출력)

1 (위치 1, 네 번째 출력)

location이 2인 작업은 첫 번째로 출력되므로, 결과는 1입니다.
