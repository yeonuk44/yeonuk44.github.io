---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_I_Hate_Even_Numbers
title: I hate even numbers (with.Java)
# title: I hate even numbers (with.Java)
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
date: 2023-12-28 09:00:00 +0900
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

## This is a post about the "I hate even numbers" problem.

We're going to learn about it by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### Problem

Complete the solution function so that, given an integer n as a parameter, it returns an array containing the odd numbers n or less in ascending order.

#### Example input and output

| n   | result                      |
| --- | --------------------------- |
| 10  | [1, 3, 5, 7, 9]             |
| 15  | [1, 3, 5, 7, 9, 11, 13, 15] |

My solution to the ### problem

```java
class Solution {
    public int[] solution(int n) {
        int[] answer;
        if(n % 2 == 0){
            answer = new int[n / 2];
        } else {
            answer = new int[n / 2 + 1];
        }

        int count = 0;
        for(int i = 1; i <= n; i++){
            if(i % 2 != 0){
                answer[count++] = i;
            }
        }
    } return answer;
}
```

#### solution description

public int[] solution(int n) : Declares a function solution, which takes a positive integer n as an input parameter. The function returns an array of integers.

int[] answer;: Declares an array of integers, answer. This array will be used later as an array to store odd numbers.

if (n % 2 == 0): If the input n is even, initialize the size of the answer array to (n / 2), since there will be (n / 2) odd numbers.

answer = new int[n / 2];: initialize the size of the array to (n / 2) when it is even.

else : If the input n is odd, initialize the size of the answer array to ((n / 2) + 1) because there will be ((n / 2) + 1) odd numbers.

answer = new int[n / 2 + 1];: Initialize the array size to ((n / 2) + 1) for odd numbers.

int count = 0;: Declare the count variable and initialize it to 0. This variable will be used when storing odd numbers in the answer array.

for (int i = 1; i <= n; i++) : Repeat for all integers from 1 to n.

if (i % 2 != 0) : If the current number i is odd, that is, when divided by 2, the remainder is 1, do the following

answer[count++] = i;: Store the current odd number i in the answer array, incrementing the count variable to indicate where to store the next odd number.

return answer;: Return the answer array filled with odd numbers as the return value of the function.
