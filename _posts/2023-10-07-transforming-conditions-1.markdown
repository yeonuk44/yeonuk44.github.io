---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Transforming_conditions_1
title: Transforming a sequence based on conditions 1, How to control an array based on conditions (with.Java)
# title: Transforming a sequence based on conditions 1, How to control an array based on conditions (with.Java)

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
date: 2023-10-07 09:00:00 +0900
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

### In this article, we learned about converting a sequence to fit a condition.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given an array of integers, arr.

For each element in arr, divide by 2 if the value is an even number greater than or equal to 50, and multiply by 2 if it is an odd number less than or equal to 50.

Complete the solution function to return the resulting array of integers.

##### Example input and output

| arr                    | result                |
| ---------------------- | --------------------- |
| [1, 2, 3, 100, 99, 98] | [2, 2, 6, 50, 99, 49] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int[] solution(int[] arr) {
        int[] answer = new int[arr.length];
        for(int i = 0; i < arr.length; i++){
            if(arr[i] >= 50 && arr[i] % 2 == 0){
                answer[i] = arr[i] / 2;
            }else if(arr[i] < 50 && arr[i] % 2 != 0){
                answer[i] = arr[i] * 2;
            }else{
                answer[i] = arr[i];
            }
        }
    } return answer;
}
```

##### Solution

int[] answer = new int[arr.length]; : Create an array answer with the same length as the input array arr to store the result.

for(int i = 0; i < arr.length; i++) : Iterate over the input array arr, examining each element.

if(arr[i] >= 50 && arr[i] % 2 == 0) : If the current element is greater than or equal to 50 and is an even number:

Store the current element divided by 2 in the answer array.

else if(arr[i] < 50 && arr[i] % 2 != 0) : If the current element is less than 50 and odd:

Store the value of the current element multiplied by 2 in the ANSWER array.

else : If the above two conditions are not satisfied (i.e., greater than 50 but not an even number, or less than 50 but not an odd number):

Store the current element as it is in the answer array.

return answer;: Returns the answer array with the operation finally completed.
