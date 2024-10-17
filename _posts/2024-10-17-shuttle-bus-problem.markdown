---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Shuttle_Bus_Problem
title: 2018 KAKAO BLIND RECRUITMENT problem, shuttle bus (with.Java)
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

## 2018 KAKAO BLIND RECRUITMENT problem, shuttle bus (with.J)

## This is an article about the 2018 KAKAO BLIND RECRUITMENT problem and shuttle bus (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Kakao runs a free shuttle bus, so you can come to the office comfortably from Pangyo Station.

Kakao's employees call each other "crews," and many crew members use these shuttles to go to work every morning.

In this problem, for convenience, let's assume that the shuttle operates under the following rules.

The shuttle arrives at the station at a total of n t-minute intervals from 09:00, and one shuttle can accommodate up to m passengers.

At the moment of arrival, the shuttle takes the crew in the queue and departs immediately.

For example, the shuttle that arrived at 09:00 can also take the crew that lined up at 09:00 if there is a seat available.

Cohn, who couldn't be bothered to get out early and wait for the shuttle, found out which crew arrived in the shuttle queue after a week of persistent observation.

Find the latest time of arrival when Cohn can take the shuttle to the office.

However, Cohn is lazy, so he stands behind the queue among the crew that arrived at the same time.

Also, all crew need to sleep so go home at 23:59.

Therefore, no crew will take the shuttle the next day.

#### Restrictions

Input Format

- The input is given the number of shuttle operations n, the shuttle operation interval t, the maximum number of crews that can be boarded in one shuttle m, and the arrangement timable, which collects the time when the crew arrives in the queue.
- 0 ＜ n ≦ 10
- 0 ＜ t ≦ 60
- 0 ＜ m ≦ 45
- The timable is an array with a minimum length of 1 and a maximum length of 2000 with the time the crew arrives in the queue in HH:MM format during the day.
- Crew's arrival time HH:MM is between 00:01 and 23:59.

Output Format

- It outputs the latest arrival time when the cone can safely take the shuttle to the office. The arrival time is in HH:MM format and can be between 00:00 and 23:59.

#### Input/output Examples

| n   | t   | m   | timetable                                                                                                                                       | answer  |
| --- | --- | --- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| 1   | 1   | 5   | ["08:00", "08:01", "08:02", "08:03"]                                                                                                            | "09:00" |
| 2   | 10  | 2   | ["09:10", "09:09", "08:00"]                                                                                                                     | "09:09" |
| 2   | 1   | 2   | ["09:00", "09:00", "09:00", "09:00"]                                                                                                            | "08:59" |
| 1   | 1   | 5   | ["00:01", "00:01", "00:01", "00:01", "00:01"]                                                                                                   | "00:00" |
| 1   | 1   | 1   | ["23:59"]                                                                                                                                       | "09:00" |
| 10  | 60  | 45  | ["23:59","23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59", "23:59"] | "18:00" |

### Problem solving

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

#### Solution Description

This article covers Java code that addresses the problem of getting passengers on the bus at a specific time.

- n: Number of buses
- t: Bus interval (minutes)
- m: Maximum number of passengers that can be carried at a time
- timable: an array of strings indicating when the crew arrives

Priority Queue is used to manage the arrival time of passengers, and each bus arrives takes available passengers out of the queue for processing.

First, sort the priority queue by putting the arrival time of the passengers.

These queues are automatically sorted in order of arrival time.

Starting at 09:00, repeat the process of getting the passenger out of the queue and boarding each bus as it arrives.

Initially, set the current time to 09:00.

After that, add t minutes to each bus's arrival to calculate the arrival time of the next bus.

If the number of minutes is more than 60, it is converted to hourly units.

Next, for each bus, take the passenger out of the queue.

Take the passengers out of the queue and board based on the maximum number of passengers m that can be loaded at a time.

For the last bus, pick up a passenger in time for the current time, or set the time to arrive a minute earlier than that passenger if the last passenger is present.

##### Logic

- Add passenger arrival time to queue
- Calculate the arrival time of each bus and handle passenger boarding
- Set Last Arrival Time
- Time conversion function
- The function sp to divide the hour, minute, transforms the time given by the string into an integer array.

##### Conclusion

This code effectively calculates the bus arrival time and passenger boarding time to find the optimal arrival time.

The process of managing the arrival time of passengers through the code and properly boarding passengers according to the arrival time of the bus was implemented.
