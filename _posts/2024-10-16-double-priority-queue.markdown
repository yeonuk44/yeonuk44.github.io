---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Double_Priority_Queue
title: Double Priority Queue (with.Java)
# title: Double Priority Queue (with.Java)
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
date: 2024-10-16 09:00:00 +0900
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

## This is an article about double priority queue (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

The dual priority queue refers to a data structure that allows you to perform the following operations.

Delete the maximum value from the D1 queue.

Delete the minimum value from the D-1 queue.

When the operation operations to be performed by the dual priority queue are given as parameters, implement a solution function to return [maximum, minimum] if the queue is empty after processing all operations.

#### Restrictions

- Operations is an array of strings that are greater than or equal to 1 million and less than or equal to 1 million.
- Elements in operations represent the operations that the queue will perform.
- Elements are given in the form of "command data." - If there are more than one maximum/minimum value in the operation to delete maximum/minimum value, delete only one.
- If an empty queue is given an operation to delete data, it ignores the operation.

#### Input/output Examples

| operations                                                                  | return     |
| --------------------------------------------------------------------------- | ---------- |
| ["I 16", "I -5643", "D -1", "D 1", "D 1", "I 123", "D -1"]                  | [0,0]      |
| ["I -45", "I 653", "D 1", "I -642", "I 45", "I 97", "D 1", "D -1", "I 333"] | [333, -45] |

### problem solving

```java
import java.util.ArrayList;
import java.util.Collections;

class Solution {
    public int[] solution(String[] operations) {
        int[] answer = {Integer.MIN_VALUE, Integer.MAX_VALUE};
        ArrayList<Integer> list = new ArrayList<>();

        for(String str : operations){
            if(str.contains("I")){
                list.add(Integer.valueOf(str.split(" ")[1]));
                Collections.sort(list);
            }
            if(str.contains("D")){
                if(list.size() == 0){continue;}
                if(str.split(" ")[1].equals("1")){
                    list.remove(list.size() - 1);
                }else{
                    list.remove(0);
                }
            }
        }


        if(list.size() == 0){
            answer[0] = 0;
            answer[1] = 0;
            return answer;
        }else{
            for(int i = 0; i < list.size(); i++){
                if(list.get(i) > answer[0]){
                    answer[0] = list.get(i);
                }
                if(list.get(i) < answer[1]){
                    answer[1] = list.get(i);
                }
            }
        }

        return answer;
    }
}
```

#### Solution Description

- Initializing variables: the answer array has the initial values of Integrer.MIN_VALUE and Integrer.MAX_VALUE.list is the ArrayList to serve as the queue.
- Handles commands: Process commands by traversing each string in the operations array. Strings containing the "I number" use split to extract numbers, add them to the list, and sort them. "D 1" deletes the maximum value and "D-1" deletes the minimum value.
- Calculate the result: Return [0, 0] if the list is empty after the command is processed. If not, it traverses the list and stores the maximum and minimum values in the answer array.

##### Conclusion

A dual priority queue can be implemented as above.

This method has the advantage of processing commands in order and simply implementing them using ArrayList.

It is a method of processing the command appropriately according to the state of the queue to derive the final result.
