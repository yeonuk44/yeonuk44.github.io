---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Monthly_Code_Challenge_Season_1_Balloon_Popping
title: Monthly Code Challenge Season 1 questions, balloon popping (with.Java)
# title: Monthly Code Challenge Season 1 questions, balloon popping (with.Java)
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
date: 2024-10-30 09:00:00 +0900
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

## Monthly Code Challenge Season 1 questions, balloon popping (with.J)

## This is what I learned about the monthly code challenge season 1 question, balloon bursting (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

There are n balloons arranged in a row.

Every balloon has a different number written on it.

You want to repeat the next process and keep popping the balloons until there is only one left.

Choose any two adjacent balloons, then burst one of them.

If a burst balloon creates an empty space between the balloons, stick the balloons close to the center to make sure there is no empty space.

There are conditions here.

The act of bursting a balloon with a smaller number among two adjacent balloons can only be done up to once.

In other words, if you burst a balloon with a smaller number among the two adjacent balloons at some point, you can then pop only the balloon with a larger number after selecting the two adjacent balloons.

You want to find out which balloons can last until the end.

If you pop a balloon according to the conditions described above, some may be left to the end, but some may not be able to leave it to the end at all costs.

An array a containing the numbers of the balloons arranged in a row is given.

Complete the solution function to return the number of balloons that can be left to the end when the balloon is popped until only one is left, according to the rules described above.

#### Restrictions

- The length of a is not less than 1 but not more than 1,000,000.
- a[i] means the number written on the i+1th balloon.
- All numbers of a are integers greater than or equal to -1,000,000 and less than or equal to 1,000,000,000.
- All numbers of a are different.

#### Input/output Examples

<!--
| Column name | Type         | Nullable |
| ----------- | ------------ | -------- |
| CAR_ID      | INTEGER      | FALSE    |
| CAR_TYPE    | VARCHAR(255) | FALSE    |
| DAILY_FEE   | INTEGER      | FALSE    |
| OPTIONS     | VARCHAR(255) | FALSE    | -->

| a                                     | result |
| ------------------------------------- | ------ |
| [9,-1,-5]                             | 3      |
| [-16,27,65,-2,58,-92,-71,-68,-61,-33] | 6      |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### problem solving

```java
class Solution {
    public int solution(int[] a) {
        int answer = 2;
        int[] left_arr = new int[a.length];
        int[] right_arr = new int[a.length];
        int left_min = a[0];
        int right_min = a[a.length - 1];

        int idx = a.length - 2;
        for(int i = 1; i < a.length - 1; i++){
            if(left_min > a[i]){
                left_min = a[i];
            }
            if(right_min > a[idx]){
                right_min = a[idx];
            }
            left_arr[i] = left_min;
            right_arr[idx--] = right_min;
        }
        if(a.length == 1){
            return 1;
        }
        for(int i = 1; i < a.length - 1; i++){
            if(left_arr[i] < a[i] && right_arr[i] < a[i]){
                continue;
            }
            answer++;
        }
        return answer;
    }
}
```

#### Solution Description

This code solves the problem of calculating the number of elements that can remain in a given array a.

The first and last elements of an array can always remain to the end.

Therefore, set the answer to 2 as the initial value.

Returns 1 as an exception if the array has a size of 1.

First, create an array left_arr that stores the minimum value from the left and an array right_arr that stores the minimum value from the right.

Left_min initializes to the first element of the array, and right_min initializes to the last element of the array.

Next, while traversing the array, update left_min and right_min.

Store the minimum value from left to current element in left_arr, and store the minimum value from right to current element in right_arr.

This will update the left_min and right_min.

It then traverses from the second element of the array to the second final element.

If the current element is greater than the values of left_arr and right_arr, it cannot remain until the end, so proceed to continue.

Otherwise, increase the answer.

Finally, return the calculated answer.

##### Conclusion

The algorithm is efficient as it performs two comparison operations on each element while traversing the array twice.
