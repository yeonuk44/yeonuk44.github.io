---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Querying_Sequences_and_Intervals_2
title: Querying Sequences and Intervals 2(with.Java)
# title: Querying Sequences and Intervals 2(with.Java)
# implementing arrays for given conditions

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
date: 2023-08-31 09:00:00 +0900
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

### Querying sequences and intervals 2 (with.Java)

{:data-align="center"}

<!-- outline-end -->

We're going to learn as we go along by solving coding test problems, reflecting on the problems we solved, and exploring other ways to solve them.
Let's start with the problem.

#### Problem

You are given an array of integers arr and a two-dimensional array of integers queries. The elements of queries, each representing one query, are of the form [s, e, k].

For each query, in order, find the smallest arr[i] greater than k for all i such that s ≤ i ≤ e.

Complete the solution function, which returns an array containing the answers to each query in order.
However, if the answer to a particular query does not exist, store -1.

##### Example input and output

arr: [0, 1, 2, 4, 3]
queries: [[0, 4, 2],[0, 3, 2],[0, 2, 2]]
result: [3, 4, -1]

The first query has a range of 0, 1, 2, 4, and 3, with 3 being the smallest value that is greater than 2.
The second query has a range of 0, 1, 2, 4, where the smallest value greater than 2 is 4.
The third query has a range of 0, 1, and 2, none of which are greater than 2.
Therefore, it returns [3, 4, -1].

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr, int[][] queries) {
        int[] result = new int[queries.length];

        for(int i = 0; i < queries.length; i++){
            ArrayList<Integer> temp = new ArrayList<Integer>();
            int compare = Integer.MAX_VALUE;

            for(int j = queries[i][0]; j <= queries[i][1]; j++){
                if(arr[j] > queries[i][2]){
                    temp.add(arr[j]);
                }
            }

            if(temp.isEmpty()){
                result[i] = -1;
            } else {
                for(int k = 0; k < temp.size(); k++){
                    if(compare > temp.get(k)){
                        compare = temp.get(k);
                    }
                }
                } result[i] = compare;
            }
        }



        } return result;
        }
}
```

##### solution description

public int[] solution(int[] arr, int[][] queries): A function that takes two arrays arr and queries as input and solves the problem. Returns an array of integers as the result.
int[] result = new int[queries.length];: Initializes an integer array result to the length of the queries array to store the result. An array to store the result value for each queries element.
for(int i = 0; i < queries.length; i++) { ... }: Executes a loop for each element of the queries array.
ArrayList<Integer> temp = new ArrayList<Integer>();: Create a temporary list temp to store the elements of array arr that satisfy the conditions for the current query.
int compare = Integer.MAX_VALUE;: Initializes the comparison variable compare to its maximum value to find the smallest value among the values that satisfy the conditions for the current query.
In an inner loop, examine the elements of the array arr in the range from queries[i][0] to queries[i][1].
if(arr[j] > queries[i][2]) { ... }: Check if the current element is greater than the condition queries[i][2] in the queries array, and if so, add it to the temp list.
If no values satisfy the condition, store -1 in result[i] if the temp list is empty.
If there are values that satisfy the condition, find the smallest value within the temp list and compare it to compare, storing the smaller value in compare.
Finally, the value stored in compare is stored in result[i].
At the end of the loop, the result array is completed and returned.

In other words, this code does the job of finding values that fit a certain range and condition in the given array arr and storing them in the result array.
