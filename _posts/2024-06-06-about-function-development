---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Function_Development
title: Function development (with.Java)
# title: Function development (with.Java)
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
date: 2024-06-06 09:00:00 +0900
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

## This article looks into the issue of “Function Development (with.Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The programmers team is working on improving the feature.

Each feature can be reflected in the service when progress is 100%.

Additionally, because the development speed of each function is different, later functions may be developed before earlier functions, and in this case, later functions are distributed together with the earlier functions.

First, complete the solution function to return how many features are deployed for each deployment, given progresses, an integer array listing the progress of the tasks in the order in which they should be deployed, and speeds, an integer array listing the development speed of each task.

#### Restrictions

- The number of tasks (length of progresses, speeds array) is less than 100.
- Work progress is a natural number less than 100.
- The work speed is a natural number less than 100.
- Distribution can only be done once per day, and is assumed to occur at the end of the day. For example, if a task is 95% complete and the development rate is 4% per day, the deployment will occur in 2 days.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| progress                 | speeds             | return    |
| ------------------------ | ------------------ | --------- |
| [93, 30, 55]             | [1, 30, 5]         | [2, 1]    |
| [95, 90, 99, 99, 80, 99] | [1, 1, 1, 1, 1, 1] | [1, 3, 2] |

### My solution to the problem

```java
import java.util.Queue;
import java.util.LinkedList;
import java.util.ArrayList;

class Solution {
 public int[] solution(int[] progresses, int[] speeds) {
 Queue<Integer> que = new LinkedList<>();

 for(int i = 0; i < progresses.length; i++){
 int temp = 100 - progresses[i];
 if(temp % speeds[i] == 0){
 que.add(temp / speeds[i]);
 }else{
 que.add(temp / speeds[i] + 1);
 }
 }

 int compare = que.poll();
 int count = 1;
 ArrayList<Integer> list = new ArrayList<>();
 while(!que.isEmpty()){
 if(compare >= que.peek()){
 count++;
 que.remove();

 }else{
 list.add(count);
 count = 1;
 compare = que.poll();
 }
 }
 list.add(count);

 int[] answer = new int[list.size()];
 for(int i = 0; i < list.size(); i++){
 answer[i] = list.get(i);
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

The solution method takes as input two arrays progresses and speeds.

The progress and pace of the tasks are used to calculate the number of days each task requires to be completed, which then calculates the number of features completed for each day.

First, we create a list of ArrayList<Integer> objects. This list stores the number of features completed for each day.

Initialize the day, count, and idx variables. day is a variable that stores the maximum number of completion days until now, and count is a variable that represents the number of functions that have been completed to date.

We start processing for each task through a for loop.

Calculate the number of days required for each task to complete, updating the count variable with this.

If the previous task has been completed (day \* speeds[i] + progresses[i] >= 100), increment the count.

Otherwise (i != 0), we add count to the list and initialize count to 1.

Calculate the number of days it will take for each task to complete and update day using this.

Calculate the number of days it will take to complete the task based on the speed, and update day only if it is greater than the maximum number of days so far.

Finally, we proceed with processing the last task. After the loop for all tasks has finished and the last task has been completed, count is added to the list.

Converts the values ​​stored in the list to an array and returns it.
