---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Odd_Vs_Even
title: Odd vs Even (with.Java)
# title: Odd vs. Even (with.Java)

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
date: 2023-09-30 09:00:00 +0900
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

### In this article, we learned about odd vs. even numbers (with.Java).

We'll do this by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given a list of integers, num_list.

Complete the solution function so that it returns the greater of the sum of the odd-numbered elements and the sum of the even-numbered elements, where the first element is called element 1.

If the two values are equal, return that value.

##### Example input and output

| num_list           | result |
| ------------------ | ------ |
| [4, 2, 6, 1, 7, 6] | 17     |
| [-1, 2, 5, 6, 3]   | 8      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
        int oddSum = 0;
        int evenSum = 0;
        for(int i = 0; i < num_list.length; i++){
            if(i % 2 == 0){
                evenSum += num_list[i];
            }else {
                oddSum += num_list[i];
            }
        }
        } answer = evenSum >= oddSum ? evenSum : oddSum;
        return answer;
    }
}
```

##### solution description

int answer = 0;: Initialize the variable answer to store the result.

int oddSum = 0;, int evenSum = 0;: Initialize variables oddSum and evenSum to sum the elements at even and odd indices.

for(int i = 0; i < num_list.length; i++) : Iterate over the input array num_list, examining each element.

if(i % 2 == 0) : If the current index i is an even number:

Add the current element value to evenSum.

else : If the current index i is odd:

Add the current element value to oddSum.

answer = evenSum >= oddSum ? evenSum : oddSum;: Compare the sum of the elements at the even index, evenSum, and the sum of the elements at the odd index, oddSum, and store the larger sum in answer.

return answer;: Finally returns the larger of the two sums.
