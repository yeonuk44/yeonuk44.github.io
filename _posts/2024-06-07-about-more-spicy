---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_More_Spicy
title: More Spicy (with.Java)
# title: More Spicy (with.Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, heap]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-06-07 09:00:00 +0900
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

## This article looks into the "Spicier (with.Java)" issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Leo, who likes spicy food, wants all his food to have a Scoville rating of K or higher.

To make all foods have a Scoville rating of K or higher, Leo creates a new food by mixing the two foods with the lowest Scoville ratings in a special way as shown below.

`Scoville number of mixed foods = Scoville number of least spicy food + (Scoville number of second least spicy food * 2)`

Leo mixes repeatedly until all the foods have a Scoville rating of K or higher.

Given the array scoville containing the Scoville index of the food Leo has and the desired Scoville index K, write a solution function to return the minimum number of times that must be mixed to make the Scoville index of all foods greater than K.

#### Restrictions

- The length of the scoville is not less than 2 but not more than 1,000,000.
- K is between 0 and 1,000,000,000.
- The scoville elements are between 0 and 1,000,000.
- If the Scoville index of all foods cannot be made above K, -1 is returned.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| scoville             | K   | return |
| -------------------- | --- | ------ |
| [1, 2, 3, 9, 10, 12] | 7   | 2      |

### My solution to the problem

```java
import java.util.PriorityQueue;

class Solution {
 public int solution(int[] scoville, int K) {
 PriorityQueue<Integer> que = new PriorityQueue<>();
 for(int i : scoville){
 que.add(i);
 }

 int answer = 0;
 while(que.peek() < K){
 que.add(que.poll() + (que.poll() * 2));
 answer++;
 if(que.size() == 1 && que.peek() < K){
 return -1;
 }
 }

 return answer;
 }
}
```

### Solved review

The solution method takes as input two arrays progresses and speeds.

It uses the progress and speed of tasks to calculate the number of days each task will need to be completed.

Creates a Queue<Integer> object que to store the number of days it will take for each task to complete.

The first for loop calculates the number of days needed for each task and stores it in que. If the number of days it takes to complete a task depending on the speed is not divisible by a decimal point, it is rounded up.

Store the required number of days for the first task in the compare variable and initialize the count variable.

Through the second while loop, it repeats until que is empty and compares the number of days it takes to complete each task.

Compare compare with the number of days required for the current task and if it is less than or equal we have completed the task so we increment the count and remove the task from the que.

Otherwise, since a new task has been started, we add the number of tasks completed so far to the list and initialize count. It also updates compare.

Finally, the values ​​stored in the list are converted to an array and returned.

This code solves the problem of calculating the number of days required for each task to complete, and calculating and returning the number of features completed for each day.

Let's solve it as an array as well.

#### My solution to the problem

```java
import java.util.ArrayList;

class Solution {
 public int[] solution(int[] progresses, int[] speeds) {

 ArrayList<Integer> list = new ArrayList<>();
 int day = 0;
 int count = 1;
 int idx = 0;
 for(int i = 0; i < progresses.length; i++){
 if(day * speeds[i] + progresses[i] >= 100){
 count++;
 }else if(i != 0){
 list.add(count);
 count = 1;
 }
 int temp = 100 - progresses[i];
 if(temp % speeds[i] == 0){
 int temp2 = temp / speeds[i];
 if(day < temp2){
 day = temp2;
 }
 }else{
 int temp2 = temp / speeds[i] + 1;
 if(day < temp2){
 day = temp2;
 }
 }
 }
 if(day * speeds[progresses.length - 1] + progresses[progresses.length - 1] >= 100){
 list.add(count);
 }



 int[] answer = new int[list.size()];
 for(int i = 0; i < list.size(); i++){
 answer[i] = list.get(i);
 }

 return answer;
 }
}
```

##### Solved review

The solution method takes as input the integer array scoville and the integer K.

Creates a priority queue PriorityQueue<Integer>.

Inserts each element of the scoville array into the priority queue.

Initialize the answer variable and repeat until the Scoville index is greater than or equal to K.

Within the loop, if the first element of the current priority queue is less than K, the two smallest values ​​are taken out, shuffled, and then reinserted into the queue. At this time, the shuffled result is calculated as the first value + (second value \* 2).

Increase the number of shuffles by 1 in answer.

If the Scoville index has not exceeded K by the end of the loop, -1 is returned.

Otherwise it returns answer.

This code solves the problem of calculating the minimum number of times food must be mixed based on given conditions.
