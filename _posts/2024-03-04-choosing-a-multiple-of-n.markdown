---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Choosing_A_Multiple_Of_N
title: Choosing a multiple of n (with.Java)
# title: Choosing a multiple of n (with.Java)
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
date: 2024-03-04 09:00:00 +0900
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

## This is an article about the problem of “Selecting a multiple of n.”

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When the integer n and the integer array numlist are given as parameters, complete the solution function to return an array with numbers that are not multiples of n removed from numlist.

#### Restrictions

- 1 ≤ n ≤ 10,000
- 1 ≤ size of numlist ≤ 100
- 1 ≤ elements of numlist ≤ 100,000

#### Input/Output Example

| n   | numlist                        | result             |
| --- | ------------------------------ | ------------------ |
| 3   | [4, 5, 6, 7, 8, 9, 10, 11, 12] | [6, 9, 12]         |
| 5   | [1, 9, 3, 10, 13, 5]           | [10, 5]            |
| 12  | [2, 100, 120, 600, 12, 12]     | [120, 600, 12, 12] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int[] solution(int n, int[] numlist) {
         int cnt = 0;
         for(int x : numlist){
             if(x % n == 0){
                 cnt++;
             }
         }
         int[] answer = new int[cnt];
         int idx = 0;
         for(int i = 0; i < numlist.length; i++){
             if(numlist[i] % n == 0){
                 answer[idx++] = numlist[i];
             }
         }
         return answer;
     }
}
```

### Solution explanation

- cnt: A variable for counting the number of numbers divisible by n. The initial value is set to 0.
- for-each loop: Remove x from the numlist array one by one and repeat.
- If the remainder when x is divided by n is 0, that is, if x is divisible by n, cnt is increased.
- Result array (answer) initialization: Use cnt to specify the size of the result array answer.
- Initialization of index variable (idx): Initialize the index variable idx to 0 to store the value in the result array answer.
- for loop: Repeats the numlist array using index i.
- If the remainder is 0 when numlist[i] is divided by n, that is, if numlist[i] is divisible by n, numlist[i] is stored in answer[idx] and idx is increased by 1.
