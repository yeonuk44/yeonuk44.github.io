---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_Largest_Number
title: Find largest number (with.Java)
# title: Find largest number (with.Java)
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
date: 2024-02-29 09:00:00 +0900
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

## This article examines the problem of “Finding the largest number.”

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When an integer array array is given as a parameter, complete the solution function to return an array containing the largest number and its index.

#### Restrictions

- 1 ≤ length of array ≤ 100
- 0 ≤ array element ≤ 1,000
- There are no duplicate numbers in the array.

#### Input/Output Example

| array          | result  |
| -------------- | ------- |
| [1, 8, 3]      | [8, 1]  |
| [9, 10, 11, 8] | [11, 2] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int[] solution(int[] array) {
         int[] answer = new int[2];
         int temp = 0;
         int idx = 0;
         for(int i = 0; i < array.length; i++){
             if(temp < array[i]){
                 temp = array[i];
                 idx = i;
             }
         }

         answer[0] = temp;
         answer[1] = idx;
         return answer;
     }
}
```

### Solution explanation

- First, an int array answer of size 2 is declared and initialized. This array is used to store the results.
- Additionally, int variables temp and idx are also declared and initialized to 0.
- temp is a variable that stores the maximum value to date, and idx is a variable that stores the index of the maximum value.
- Next, iterate over the array using a for statement.
- Access each element of the array and compare it to temp. If the current element is greater than temp, update temp and idx.
- In other words, when a value larger than the current maximum value is encountered, temp and idx are updated and the corresponding value and index are recorded.
- When the for statement ends, temp and idx will have the largest value and the index of that value.
- Store this value in the answer array and return the answer array.
