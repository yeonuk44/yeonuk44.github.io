---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Shuttle_Bus_Problem
title: 2018 KAKAO BLIND RECRUITMENT 문제, 셔틀버스 (with.Java)
# title: 2018 KAKAO BLIND RECRUITMENT problem, shuttle bus (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, queue]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-17 09:00:00 +0900
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

## 2018 KAKAO BLIND RECRUITMENT 문제, 셔틀버스 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

카카오에서는 무료 셔틀버스를 운행하기 때문에 판교역에서 편하게 사무실로 올 수 있다.

카카오의 직원은 서로를 '크루'라고 부르는데, 아침마다 많은 크루들이 이 셔틀을 이용하여 출근한다.

이 문제에서는 편의를 위해 셔틀은 다음과 같은 규칙으로 운행한다고 가정하자.

셔틀은 09:00부터 총 n회 t분 간격으로 역에 도착하며, 하나의 셔틀에는 최대 m명의 승객이 탈 수 있다.

셔틀은 도착했을 때 도착한 순간에 대기열에 선 크루까지 포함해서 대기 순서대로 태우고 바로 출발한다.

예를 들어 09:00에 도착한 셔틀은 자리가 있다면 09:00에 줄을 선 크루도 탈 수 있다.

일찍 나와서 셔틀을 기다리는 것이 귀찮았던 콘은, 일주일간의 집요한 관찰 끝에 어떤 크루가 몇 시에 셔틀 대기열에 도착하는지 알아냈다.

콘이 셔틀을 타고 사무실로 갈 수 있는 도착 시각 중 제일 늦은 시각을 구하여라.

단, 콘은 게으르기 때문에 같은 시각에 도착한 크루 중 대기열에서 제일 뒤에 선다.

또한, 모든 크루는 잠을 자야 하므로 23:59에 집에 돌아간다.

따라서 어떤 크루도 다음날 셔틀을 타는 일은 없다.

#### 제한사항

입력 형식

- 셔틀 운행 횟수 n, 셔틀 운행 간격 t, 한 셔틀에 탈 수 있는 최대 크루 수 m, 크루가 대기열에 도착하는 시각을 모은 배열 timetable이 입력으로 주어진다.
- 0 ＜ n ≦ 10
- 0 ＜ t ≦ 60
- 0 ＜ m ≦ 45
- timetable은 최소 길이 1이고 최대 길이 2000인 배열로, 하루 동안 크루가 대기열에 도착하는 시각이 HH:MM 형식으로 이루어져 있다.
- 크루의 도착 시각 HH:MM은 00:01에서 23:59 사이이다.

출력 형식

- 콘이 무사히 셔틀을 타고 사무실로 갈 수 있는 제일 늦은 도착 시각을 출력한다. 도착 시각은 HH:MM 형식이며, 00:00에서 23:59 사이의 값이 될 수 있다.

#### 입출력 예

<!-- | operations                                                                  | return     |
| --------------------------------------------------------------------------- | ---------- |
| ["I 16", "I -5643", "D -1", "D 1", "D 1", "I 123", "D -1"]                  | [0,0]      |
| ["I -45", "I 653", "D 1", "I -642", "I 45", "I 97", "D 1", "D -1", "I 333"] | [333, -45] | -->

| n   | t   | m   | timetable                                                                                                                                       | answer  |
| --- | --- | --- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| 1   | 1   | 5   | ["08:00", "08:01", "08:02", "08:03"]                                                                                                            | "09:00" |
| 2   | 10  | 2   | ["09:10", "09:09", "08:00"]                                                                                                                     | "09:09" |
| 2   | 1   | 2   | ["09:00", "09:00", "09:00", "09:00"]                                                                                                            | "08:59" |
| 1   | 1   | 5   | ["00:01", "00:01", "00:01", "00:01", "00:01"]                                                                                                   | "00:00" |
| 1   | 1   | 1   | ["23:59"]                                                                                                                                       | "09:00" |
| 10  | 60  | 45  | ["23:59","23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59"] | "18:00" |

### 문제 풀이

```java
import java.util.PriorityQueue;
class Solution {
    public String solution(int n, int t, int m, String[] timetable) {
        String answer = "";
        PriorityQueue<String> que = new PriorityQueue<>();
        for(String str : timetable){
            que.offer(str);
        }
        int current_hour = 0;
        int current_min = 0;
        int temp_hour = 0;
        int temp_min = 0;
        int current_passenger_time_hour = 0;
        int current_passenger_time_min = 0;
        int count = 0;
        String a_hour = "";
        String a_min = "";

        for(int i = n; i > 0; i--){
            if(i == n){
                current_hour = sp("09:00")[0];
                current_min = sp("09:00")[1];
            }else{
                current_min += t;
                if(current_min / 60 > 0){
                    current_hour += current_min / 60;
                    current_min = current_min % 60;
                }
            }
            count = 0;
            if(m <= timetable.length){
                for(int j = 0; j < m; j++){
                    if(que.isEmpty()){
                        break;
                    }
                    current_passenger_time_hour = sp(que.peek())[0];
                    current_passenger_time_min = sp(que.peek())[1];

                    if(i == 1 && count == m - 1){
                        if(current_passenger_time_hour <= current_hour){
                            current_hour = current_passenger_time_hour;
                            current_min = current_passenger_time_min - 1;
                        }
                        if(current_min < 0){
                            current_hour -= 1;
                            current_min = 59;
                            j = m - 1;
                        }
                    }
                    if(current_passenger_time_hour < current_hour){
                         que.poll();
                        count += 1;
                    }else if(current_passenger_time_hour == current_hour && current_passenger_time_min <= current_min){
                        que.poll();
                        count += 1;
                    }
                }
            }else{
                if(n == 1){
                    break;
                }
            }
        }
        if(current_hour / 10 == 0){
            a_hour = "0" + current_hour;
        }else{
            a_hour = "" + current_hour;
        }
        if(current_min / 10 == 0){
            a_min = "0" + current_min;
        }else{
            a_min = "" + current_min;
        }
        answer = a_hour + ":" + a_min;

        return answer;
    }

    public int[] sp(String str){
        int[] current_time = new int[2];
        current_time[0] = Integer.valueOf(str.split(":")[0]);
        current_time[1] = Integer.valueOf(str.split(":")[1]);

        return current_time;
    }
}
```

#### 풀이 설명

이 글에서는 특정 시간에 맞춰 버스에 승객을 태우는 문제를 해결하는 Java 코드를 다룹니다.

- n: 버스의 대수
- t: 버스 간격 (분 단위)
- m: 한 번에 태울 수 있는 최대 승객 수
- timetable: 크루가 도착하는 시각을 나타내는 문자열 배열

PriorityQueue를 사용해 승객의 도착 시간을 관리하고, 각 버스가 도착할 때마다 탑승할 수 있는 승객을 큐에서 꺼내어 처리합니다.

먼저, PriorityQueue에 승객의 도착 시간을 넣어 정렬합니다.

이 큐는 도착 시간 순으로 자동 정렬됩니다.

09:00부터 시작하여 각 버스가 도착할 때마다 큐에서 승객을 꺼내어 탑승시키는 작업을 반복합니다.

처음에는 현재 시간을 09:00으로 설정합니다.

이후 각 버스가 도착할 때마다 t분을 더하여 다음 버스의 도착 시간을 계산합니다.

만약 분이 60 이상이 되면 시간 단위로 변환합니다.

다음으로, 각 버스에 대해 큐에서 승객을 꺼내는 작업을 합니다.

한 번에 태울 수 있는 최대 승객 수 m을 기준으로 승객을 큐에서 꺼내어 탑승시킵니다.

마지막 버스의 경우, 현재 시간에 맞춰 승객을 태우거나, 만약 마지막 승객이 있는 경우 해당 승객보다 1분 일찍 도착하도록 시간을 설정합니다.

##### 로직

- 큐에 승객 도착 시간 추가
- 각 버스 도착 시간 계산 및 승객 탑승 처리
- 최종 도착 시간 설정
- 시간 변환 함수
- 시, 분을 나누기 위한 함수 sp는 문자열로 주어진 시간을 정수 배열로 변환합니다.

##### 결론

이 코드는 버스 도착 시간과 승객 탑승 시간을 효과적으로 계산하여 최적의 도착 시간을 찾습니다.

코드를 통해 승객의 도착 시간을 관리하고, 버스의 도착 시간에 맞춰 승객을 적절히 탑승시키는 과정을 구현하였습니다.
