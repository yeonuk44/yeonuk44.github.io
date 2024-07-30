---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Athletes_Problem
title: Athletes who did not finish the race (with.Java)
# title: Athletes who did not finish the race (with.Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, hash]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-06-01 09:00:00 +0900
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

## This article looks into the "Athletes who did not finish the race (with.Java)" issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Numerous marathon runners participated in the marathon.

All but one athlete completed the marathon.

When given an array participant containing the names of athletes who participated in the marathon and an array completion containing the names of athletes who completed the marathon, write a solution function to return the names of athletes who did not complete the marathon.

#### Restrictions

- The number of athletes participating in the marathon race is between 1 and 100,000.
- The length of completion is 1 less than the length of the participant.
- The participant's name must consist of at least 1 and not more than 20 lowercase letters.
- Among the participants, there may be people with the same name.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| participant                                       | completion                               | return   |
| ------------------------------------------------- | ---------------------------------------- | -------- |
| ["leo", "kiki", "eden"]                           | ["eden", "kiki"]                         | "leo"    |
| ["marina", "josipa", "nikola", "vinko", "filipa"] | ["josipa", "filipa", "marina", "nikola"] | "vinko"  |
| ["mislav", "stanko", "mislav", "ana"]             | ["stanko", "ana", "mislav"]              | "mislav" |

### My solution to the problem

```java
import java.util.*;

class Solution {
 public String solution(String[] participant, String[] completion) {
 String answer = "";
 HashMap<String, Integer> map = new HashMap<>();

 for(String temp1 : participant){
 map.put(temp1, map.getOrDefault(temp1, 0) + 1);
 }
 for(String temp2 : completion){
 map.put(temp2, map.get(temp2) - 1);
 }

 for(String key : map.keySet()){
 if(map.get(key) > 0){
 answer = key;
 }
 }
 return answer;
 }
}
```

### Solved review

The solution method receives a participant array and a completion array as input.

We will initialize the answer variable, which will store the name of the missing participant.

Creates a HashMap<String, Integer> object map. Where String is the participant's name, and Integer represents the number of occurrences of that name.

In the first for loop, it iterates over each element of the participant array, uses the name as a key in the map, and stores the number of occurrences of that name as the value. If the name already exists in the map, the number of appearances is increased.

The second for loop iterates through each element of the completion array and decrements the number of occurrences of that name if it exists in the map.

The third for loop iterates through all keys in the map, looking for occurrences greater than 0, i.e. names of participants who did not finish. Save this name as answer.

Finally, it returns an answer.

In other words, this code is used to solve the problem of finding missing participants by comparing the names of participants and finishers.
