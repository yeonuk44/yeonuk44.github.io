---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Transforming_conditions_2
title: Transforming a sequence based on conditions 2 (with.Java)
# title: Transforming a sequence based on conditions 2 (with.Java)

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
date: 2023-10-08 09:00:00 +0900
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

For each element in arr, divide by 2 if the value is an even number greater than or equal to 50, multiply by 2 if it is an odd number less than 50, and add 1 again.

The array resulting from repeating these operations x times is denoted arr(x), and there will always be an x such that arr(x) = arr(x + 1).

Complete the solution function to return the smallest of these x's.

Note that the "=" for the two arrays means that the two arrays are the same size, and that the elements at the same index are equal to each other.

##### Example input and output

| arr                    | result |
| ---------------------- | ------ |
| [1, 2, 3, 100, 99, 98] | 5      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public int solution(int[] arr) {
        int answer = 0;
        int[] tempArr = new int[arr.length];
        do {
            for(int i = 0; i < arr.length; i++){
            tempArr[i] = arr[i];
            }
            for(int i = 0; i < arr.length; i++){
                if(arr[i] >= 50 && arr[i] % 2 == 0){
                    arr[i] = arr[i] / 2;
                } else if(arr[i] < 50 && arr[i] % 2 != 0){
                    arr[i] = arr[i] * 2 + 1;
                }
            }
            answer++;
        } while(!Arrays.equals(tempArr, arr));
        return answer - 1;
    }
}
```

##### Solution

The answer variable stores the number of times the conversion process is repeated.

The array tempArr is a temporary array for copying the current arr array value.

The do-while loop runs until tempArr and the arr array are not equal.

The first for loop copies the values in the current arr array into the tempArr array.

The second for loop changes the arr array by performing an operation based on the condition for each element.

We record the number of iterations by incrementing answer.

Arrays.equals(tempArr, arr) compares the arrays tempArr and arr to see if they are equal. If they are not equal, the loop continues.

When the loop ends, it returns answer - 1, which is the number of conversions.

As I was writing the code, I realized that I should be careful with references to arrays.

Here's an example: ###### Be careful when copying arrays

**Example**

```java
 int[] intArray1 = new int[] { 1, 2, 3 };
  int[] intArray2 = new int[] { 1, 2, 3 };

if(intArray1 == intArray2) {
    System.out.println("The two arrays are equal.");
  } else {
    System.out.println("The two arrays are not equal.");
  }
}

// return: The two arrays are not equal.
```

**Why?**

The reason is that in Java, arrays are considered objects, and array variables are references that point to array objects.

So when you use the == operator to compare array variables, you are actually comparing reference addresses.

This is a rule that applies to all objects in Java, so arrays at different memory locations are always judged to be unequal when compared with the == operator, even if their contents are identical.

This behavior is caused by Java's object comparison rules, which apply to all objects, not just arrays.

To compare the contents of objects for equality, you must use the Arrays.equals() method or a method that compares the elements of the array directly.

Other languages have mostly similar behaviors, although some languages may have subtle differences in these behaviors.

However, since most comparisons of objects are based on reference addresses, the general principle will be similar: the value of a variable of a reference type is the address of the object in the Heap area, so the return result will be different because you are comparing the value of the address, not the value of the element.

This applies not only to arrays, but also to types like strings that compare objects.
