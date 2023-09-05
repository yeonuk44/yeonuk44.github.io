---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Creating_A_Collatz_Sequence
title: Creating a Collatz Sequence (with.Java)
# title: Creating a Collatz Sequence (with.Java)

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
date: 2023-09-04 09:00:00 +0900
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

### In this article, we learned how to create a Collatz sequence (with.Java).

{:data-align="center"}

<!-- outline-end -->

We're going to learn as we go by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.
Let's start with the problem.

#### Problem

The problem of asking whether, for any natural number x, if the current value is x, if we keep repeating the calculation of dividing by 2 if x is even and replacing it with 3 \* x + 1 if x is odd, we will surely end up with x = 1 at some point is called the Collatz problem.
And the sequence that records all the numbers we've gone through is called the Collatz sequence.
We know that for any number less than or equal to 1,000, we will reach 1 at some point.
Given an arbitrary positive integer n less than or equal to 1,000, complete the solution function to return the Collatz sequence with initial value n.

##### Example input and output

n: 10
result: [10, 5, 16, 8, 4, 2, 1]

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
import java.util.*;

class Solution {
    public int[] solution(int n) {
        ArrayList<Integer> temp = new ArrayList<Integer>();
        temp.add(n);

        while(n != 1){
            if(n % 2 == 0){
                n = n / 2;
            } else {
                n = 3 * n + 1;
            }
            temp.add(n);
        }

        int[] answer = new int[temp.size()];
        for(int i = 0; i < temp.size(); i++){
            answer[i] = temp.get(i);
        }

        } return answer;
    }
}
```

##### Solution

ArrayList<Integer> temp = new ArrayList<Integer>();: Create an ArrayList object temp to store the integers.
temp.add(n);: Adds the initial integer n to the list temp. This list will store all the values from the guessing process.
while(n != 1): Start a loop that iterates until n equals 1. Transform n according to the Collatz conjecture, and exit the loop when n equals 1.
if(n % 2 == 0): Check if n is an even number. If it is, divide n by 2 to make it an odd number.
else { n = 3 \* n + 1; }: If n is odd, multiply n by 3 and add 1 to make it even.
temp.add(n);: Add the converted value of n to the temp list.
int[] answer = new int[temp.size()];: Create an integer array answer that fits the size of the temp list.
for(int i = 0; i < temp.size(); i++){ answer[i] = temp.get(i); }: Copy the values from the temp list into the array answer.
return answer;: Return the array answer where the result of the Collatz guess is stored.
