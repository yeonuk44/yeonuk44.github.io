---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_Divisors
title: Finding divisors (with.Java)
# title: Finding divisors (with.Java)
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
date: 2024-02-25 09:00:00 +0900
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

## This is an article about the problem of “finding divisors.”

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When the integer n is given as a parameter, complete the solution function to return an array containing the divisors of n in ascending order.

#### Restrictions

- 1 ≤ n ≤ 10,000

#### Input/Output Example

| n   | result                     |
| --- | -------------------------- |
| 24  | [1, 2, 3, 4, 6, 8, 12, 24] |
| 29  | [1, 29]                    |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int[] solution(int n) {
         int cnt = 0;
         for(int i = 1; i <= n; i++){
             if(n % i == 0){
                 cnt++;
             }
         }
         int[] answer = new int[cnt];
         int idx = 0;
         for(int i = 1; i <= n; i++){
             if(n % i == 0){
                 answer[idx++] = i;
             }
         }
         return answer;
     }
}
```

### Solution explanation

- Declare the cnt variable and initialize it to 0. This variable is used to count the number of divisors.
- Execute a for statement that repeats from 1 to n. The variable i has values from 1 to n. If the remainder of dividing n by i is 0, that is, if i is a divisor of n,
  Increase the cnt value by 1.
- Declare an array answer of cnt length.
- Declare the idx variable and initialize it to 0. This variable points to an index in the answers array.
- Execute a for statement that repeats from 1 to n. The variable i has values from 1 to n. If the remainder of dividing n by i is 0, that is, if i is a divisor of n,
- Assign the value i to the idx index of the answer array and increase the idx value by 1.
- Returns an array of answers.
