---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sequence_With_An_Interval_Query_1
title: How to control a sequence with an interval query 1(with.Java)

# title: About browser

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
date: 2023-08-28 09:00:00 +0900
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

### How to control a sequence with interval queries 1(with.Java)

{:data-align="center"}

<!-- outline-end -->

We're going to learn by solving a coding test problem, doing a retrospective on the problem we solved, and looking at other ways to solve it.
Let's start with the problem.

#### Problem

You are given an array of integers arr and a two-dimensional array of integers queries. The elements of queries, each representing one query, are of the form [s, e, k].

For each query, in order, find the smallest arr[i] greater than k for all i such that s ≤ i ≤ e.

Complete the solution function, which returns an array containing the answers to each query in order.
However, if the answer to a particular query does not exist, store -1.

**Caveat** If you get this wrong, you might think this is a problem of comparing values. In essence, it's a problem that is solved by finding a number greater than k for the range s and e **index**, and storing the smallest of all such numbers in an array. I hope this is not misunderstood.

##### Example input and output

arr: [0, 1, 2, 4, 3]
queries: [[0, 4, 2],[0, 3, 2],[0, 2, 2]]
result: [3, 4, -1]

The first query has a range of 0, 1, 2, 4, and 3, with 3 being the smallest value that is greater than 2.
The second query has a range of 0, 1, 2, 4, where the smallest value greater than 2 is 4.
The third query has a range of 0, 1, and 2, none of which are greater than 2.
Therefore, it returns [3, 4, -1].

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

##### Explain your solution

I'll try to explain as much as I can about the code I wrote and why I wrote it this way.
First, we declare a result of type int[] to store the result, and we need the size of the array to be as long as the elements of queries, so we enter queries.length.
Then we declare a loop to iterate through the queries, and in the process, we declare a temporary ArrayList type, temp, to store the calculated value.
We also declare a compare variable of type int to compare the smallest numbers.
Since the purpose of declaring the compare variable is to store the smallest number, we assign it an initial value of Integer.MAX_VALUE, a constant that represents the maximum value of the data type.
We then enter a loop to extract the index corresponding to the specified range of values in queries, the range s<=i<=e.
In this iteration, we store the number greater than k specified in queries into temp, which we declared earlier to be a temporary storage space.
After storing all the values that satisfy the condition, since we had a condition to return -1 if none existed, we use the ArrayList.isEmpty() function to throw an exception to return -1 if the value is empty, and if the value exists, we write a loop that iterates over the number of numbers that satisfy all the conditions.
We then determined the smallest number by storing that value in compare if it was less than compare, and then we simply stored the value in compare in result.
