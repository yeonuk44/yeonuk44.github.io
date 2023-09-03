---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_Arrays_For_Given_Conditions
title: Implementing arrays for given conditions (with.Java)
# title: Implementing arrays for given conditions (with.Java)
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
date: 2023-08-30 09:00:00 +0900
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

### In this article, we learned about Implementing an array for a given condition (with.Java)

{:data-align="center"}

<!-- outline-end -->

We're going to learn as we go by solving coding test questions, reflecting on the problems we solved, and exploring other ways to solve them.
Let's start with the problem.

#### Problem

You are given an array of integers, arr. You want to create a new array, stk, from arr.

Create a variable i, set its initial value to 0, and if i is less than the length of arr, repeat the following operations.

If stk is an empty array, add arr[i] to stk and add 1 to i. If not, add arr[i] to stk.
If stk has elements, and the last element in stk is smaller than arr[i], add arr[i] to the end of stk and add 1 to i.
If there are elements in the stk and the last element in the stk is greater than or equal to arr[i], remove the last element from the stk.
After doing the above, complete the solution function that returns the created stk.

##### Example input and output

arr: [1, 4, 2, 5, 3]
result: [1, 2, 3]

Representing the change in the array after each operation, the table looks like this

| i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     |
| 2   | 2      | [1,4]   |
| 2   | 2      | [1]     |
| 3   | 5      | [1,2]   |
| 4   | 3      | [1,2,5] |
| 4   | 3      | [1,2]   |
| -   | -      | [1,2,3] |

So it returns [1, 2, 3].

#### My solution to the problem

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr) {
        ArrayList<Integer> temp = new ArrayList<Integer>();
        for(int i = 0; i < arr.length; i++){
            if(temp.isEmpty()){
                temp.add(arr[i]);
                continue;
            }
            while(temp.get(temp.size()-1) >= arr[i]){
                temp.remove(temp.size()-1);
                if(temp.isEmpty()){
                    temp.add(arr[i]);
                    break;
                }
            }
            if(temp.get(temp.size()-1) < arr[i]){
                temp.add(arr[i]);
                continue;
            }
        }
        } int[] answer = new int[temp.size()];
        for(int j = 0; j < temp.size(); j++){
            answer[j] = temp.get(j);
        }
        } return answer;
    }
}
```

##### Explanation of the solution

The code I wrote, like all code, had to take into account the order of execution. One of the conditions is "If stk has elements and the last element of stk is greater than or equal to arr[i], then remove the last element of stk from stk." In order to satisfy this condition, I had to think of a specific input/output test case that would require me to keep deleting elements of an array, and if I kept emptying the elements in the array, I would eventually add elements of arr to the empty array.

Let's continue with the code: the isEmpty() function adds an element to the empty array with add(arr[i]). We used continue because we need to move on to the next index based on a later condition.
Here's the part about deleting elements that I had trouble with. In the problem, the condition to add an element was pre-defined, but we implemented it by considering the order of execution. To explain, we used a while statement to delete the last element of temp if the value of arr[i] is greater than or equal to the value of arr[i]. If we simply delete it, the array may run out of size depending on the specific test case. This is because we keep deleting the last element, which can result in an empty array and an ArrayList with a negative index. To make it easier to understand, we can simply compare it to another test case: if the value of arr is [2, 3, 4, 2, 1], then the return will be [1] based on the condition in the problem. In that case, the flow of index would be i=0 [2], i=1 [2,3], i=2 [2,3,4], i=3 [2,3], [2], [],[2] i=4 [],[1] eventually returning [1]. As you can see from the flow, the special test case creates an empty array, which can be a problem if you're checking for the last element through size, or if you add the last element when it's empty, arr[i] = 1, or if the element you're comparing is also [1], you can get stuck in an infinite loop in the while, etc.

The bottom line is that adding an element after the logic that simply removes it does not catch an exception, so to prevent the case of an empty array, we add the element when it is empty, force the while statement to exit, and use a break statement. In the following code, I wrote logic to traverse the loop with continue if the condition that needs to be removed is not met, i.e., if the last element in the array where the result is stored is less than arr[i], then add that element, otherwise continue. This was a problem that I approached simply and then had to think about exception handling in many test cases.
