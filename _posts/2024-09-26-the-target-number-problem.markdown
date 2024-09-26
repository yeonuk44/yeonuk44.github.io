---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Target_Number_Problem
title: Target number (with.Java)
# title: Target number (with.Java)
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
date: 2024-09-26 09:00:00 +0900
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

## I learned about the target number (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

There are n nonnegative integers.

You want to create a target number by adding or subtracting these integers appropriately without changing the order.

For example, to create a number 3 with [1, 1, 1, 1, 1, 1], you can use the following five methods.

-1+1+1+1+1 = 3

+1-1+1+1+1 = 3

+1+1-1+1+1 = 3

+1+1+1-1+1 = 3

+1+1+1+1-1 = 3

Write a solution function to return the number of ways to create a target number by adding and subtracting numbers appropriately when the array numbers contain usable numbers, and target number targets are given as parameters.

#### Restrictions

- The number of numbers given is 2 or more and 20 or less.
- Each number is a natural number greater than or equal to 1 and less than or equal to 50.
- The target number is a natural number of 1 or more and 1000 or less.

#### Input/output Examples

<!-- | prices          | return          |
| --------------- | --------------- |
| [1, 2, 3, 2, 3] | [4, 3, 1, 1, 0] | -->

| numbers         | target | return |
| --------------- | ------ | ------ |
| [1, 1, 1, 1, 1] | 3      | 5      |
| [4, 1, 2, 1]    | 4      | 2      |

### problem solving

```java
class Solution {
    static int answer;
    public int solution(int[] numbers, int target) {
        answer = 0;
        dfs(numbers, target, 0, 0);
        return answer;
    }
    public void dfs(int[] numbers, int target, int depth, int total){
        if(numbers.length == depth){
            if(total == target){
                answer++;
            }
        }else{
            dfs(numbers, target, depth + 1, total + numbers[depth]);
            dfs(numbers, target, depth + 1, total - numbers[depth]);
        }
    }
}
```

#### Solution Description

1. Declaring Classes and Variables
   class Solution: Class for troubleshooting.
   static intanswer: The static variable answer stores the number of times a target number can be created.
2. solution method
   public int solution (int[] numbers, int target): Returns the number of times a target number can be created by taking a given numeric array of numbers and a target numeric target as input.
   answer = 0: Initializes the number of cases.
   dfs(numbers, target, 0, 0): Initiates a depth-first search; sets the initial depth to 0, and the initial total to 0.
   return answer—Returns the number of cases finally calculated.
3. dfs method
   public void dfs (int[] numbers, int target, int depth, inttotal): a recursive method that performs depth-first navigation.
   if (number.length == depth): Verify that the end of the array has been reached.
   if (total == target): Increase the number of cases where the current total equals the target number target.
   else: If you have not reached the end of the array, proceed to the next step.
   dfs (number, target, depth + 1, total + numbers [depth]): Explore the case of adding the current number.
   dfs (number, target, depth + 1, total-number[depth]): Explore the case where the current number is subtracted.

#### Conclusion

This code uses DFS to explore all possible cases and to calculate the number of cases that match the target number.

Given a given numerical array and a target number, this code can efficiently determine the number of cases in which a target number can be created.
