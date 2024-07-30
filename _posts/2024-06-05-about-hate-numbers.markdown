---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Hate_Same_Numbers
title: I hate same numbers (with.Java)
# title: I hate same numbers (with.Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, stack]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-06-05 09:00:00 +0900
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

## This article looks into the problem of “I don’t like numbers that are the same (with.Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

You are given an array arr.

Each element of the array arr consists of the numbers 0 to 9.

At this time, we want to remove all but one number that appears consecutively in the array arr.

However, when returning the remaining numbers after removal, the order of the elements of the array arr must be maintained.

For example

- If arr = [1, 1, 3, 3, 0, 1, 1], it returns [1, 3, 0, 1].
- If arr = [4, 4, 4, 3, 3], it returns [4, 3].
- Complete the solution function that removes consecutive numbers from the array arr and returns the remaining numbers.

#### Restrictions

- Size of array arr: natural number less than 1,000,000
- Size of element of array arr: integer greater than or equal to 0 and less than or equal to 9

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| arr             | answer    |
| --------------- | --------- |
| [1,1,3,3,0,1,1] | [1,3,0,1] |
| [4,4,4,3,3]     | [4,3]     |

### My solution to the problem

```java
import java.util.*;

public class Solution {
 public int[] solution(int []arr) {
 Stack<Integer> stack = new Stack<Integer>();
 stack.push(arr[0]);
 for(int i = 1; i < arr.length; i++){
 if(stack.peek() != arr[i]){
 stack.push(arr[i]);
 }
 }

 int[] answer = new int[stack.size()];
 for(int i = stack.size() - 1; i >= 0; i--){
 answer[i] = stack.pop();
 }

 return answer;
 }
}
```

### Solved review

The solution method takes an integer array arr as input.

Creates a stack of Stack<Integer> objects to remove duplicate values ​​and maintain order.

Adds the first element of the given array to the stack.

This is because during the process of removing duplicate values, the first element is treated as a non-duplicate value.

The second for loop iterates through the array, adding to the stack only if the top element of the stack is different from its current value. This will help you remove duplicate values.

After duplicate values ​​are removed, when inserting the values ​​stored in the stack into an array, the pop() method is used to retrieve and store the values ​​in reverse order.

Finally, it returns the array stored in reverse order.

This code removes duplicate values ​​and uses a stack to maintain order, leaving only one duplicate value and removing the rest.

Let's solve it as an array as well.

#### My solution to the problem

```java
import java.util.*;

public class Solution {
 public int[] solution(int []arr) {
 ArrayList<Integer> list = new ArrayList<>();
 list.add(arr[0]);
 for(int i = 1; i < arr.length; i++){
 if(arr[i - 1] != arr[i]){
 list.add(arr[i]);
 }
 }

 int[] answer = new int[list.size()];
 for(int i = 0; i < answer.length; i++){
 answer[i] = list.get(i);
 }

 return answer;
 }
}
```

##### Solved review

The solution method takes an integer array arr as input.

Create an ArrayList<Integer> object list to store the results of removing duplicate values.

Adds the first element of the given array to list. This is because during the process of removing duplicate values, the first element is treated as a non-duplicate value.

The second for loop iterates through the array, adding to the list only if the previous and current values ​​are different. This will help you remove duplicate values.

Finally, the values ​​stored in the list are converted to an array and returned.

This code uses a simple method to remove duplicate values, using an ArrayList to leave only one duplicate value and remove the rest.
