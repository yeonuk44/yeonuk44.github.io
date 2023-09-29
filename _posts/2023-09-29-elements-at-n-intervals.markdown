---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Elements_At_n_Intervals
title: Elements at n intervals (with.Java)
# title: Elements at n intervals (with.Java)

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
date: 2023-09-29 09:00:00 +0900
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

### In this article, we looked at the elements of n intervals (with.Java).

We'll be solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given an integer list num_list and an integer n, complete the solution function so that it returns a list containing the elements stored in n intervals from the first element in num_list to the last element.

##### Example input and output

num_list: [4, 2, 6, 1, 7, 6]

n: 2

result: [4, 6, 7]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int answerLength = (int) Math.ceil((double) num_list.length / n);
        int[] answer = new int[answerLength];

        for (int i = 0; i < num_list.length; i += n) {
            int index = i / n;
            answer[index] = num_list[i];
        }

        } return answer;
    }
}
```

##### solution description

int answerLength = (int) Math.ceil((double) num_list.length / n);:

This part calculates the length of the new array answer.

The num_list.length represents the length of the input array num_list.

n is the given interval.

We divide it and perform a rounding operation to set the length so that we can fit all the remaining elements into the array.

int[] answer = new int[answerLength];:

Create the answer array based on the calculated answerLength.

This is the array that will eventually hold the elements extracted from num_list.

for (int i = 0; i < num_list.length; i += n) {:

This is the iteration part, which traverses the input array num_list, extracting elements at intervals n.

At the beginning of the iteration, i starts at 0.

int index = i / n;:

Calculate the index at which to store the element into the answer array.

Currently, i represents the index in num_list, which we need to store every n intervals, so we compute index.

index represents the index in the answer array.

answer[index] = num_list[i];:

Store the elements extracted from num_list in the answer array using the calculated index.

Extract the element located at index i and store it at position index in the answer array.

return answer;:

After executing all the iterations, the answer array contains the elements extracted from num_list at interval n.

Finally, we print the result by returning the answer array.

This code performs the task of extracting elements every interval n from the input array num_list and storing them in the answer array. This ensures that the ANSWER array contains the elements extracted from the input array at the desired interval in order.Performs the function of returning a column.
