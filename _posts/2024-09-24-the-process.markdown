---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Process
title: Process (with. Java)
# title: Process (with. Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, queue, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-09-24 09:00:00 +0900
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

## I learned about the process (with. Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

One of the roles of the operating system is to efficiently manage the resources of the computer system.

In this problem, you can figure out how many times a particular process runs if the operating system manages the process according to the following rules.

1. Pull one pending process out of the queue for execution.
2. If any of the processes that are waiting in the queue have a higher priority, put the processes that were just pulled back into the queue.
3. If you don't have such a process, run the one you just pulled out.
   3.1 Once the process has been executed, it will not be queued again, but will still be finished.
   For example, if four processes [A, B, C, and D] are queued in order, and the priority is [2, 1, 3, 2], they are executed in order [C, D, A, B].

Write a solution function to return how many times the process is executed, given array priorities that contain the importance of the process currently in the queue in order, and a location that tells you where the process is to be executed.

#### Restrictions

- The length of priorities is greater than 1 and less than 100.
- Elements in priorities are integers greater than 1 and less than 9.
- Elements in priorities indicate priority, and the larger the number, the higher the priority.
- location has a value greater than or equal to 0 (number of processes in standby queue - 1).
- 0 if it's at the front of priorities, 1 if it's at the second... It's expressed like this.

#### Input/output Examples

| priorities         | location | return |
| ------------------ | -------- | ------ |
| [2, 1, 3, 2]       | 2        | 1      |
| [1, 1, 9, 1, 1, 1] | 0        | 5      |

### problem solving

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

#### Solution Description

This code solves the problem of handling the job priority for the printer.

The process of calculating the given task priority arrangement and the number of times the task in a particular location is output is implemented as follows.

Code description

Required Library Import

Gets the Queue, LinkedList, Collections, Arrays library.

Method definition

Defines a solution method and receives int[] priorities and int location as inputs.

Initializes the variable answer.

This is the final value to return, which indicates how many times a particular job is output.

Queue Initialization

Create a queue of type Queue<Integer>.

Store the priority of the location location in the want_num variable.

Insert each element of the priorities array into the queue, and store the number of elements greater than or equal to the want_num in the count variable.

If the count is 0, this means that want_num is the highest priority, so return 1.

Arrange Priority Arrangements

in descending order of priorities arrangement
