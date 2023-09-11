---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_Flipping_String_Multiple_Times
title: Implementing Flipping a String Multiple Times (with.Java)
# title: Implementing Flipping a String Multiple Times (with.Java)

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
date: 2023-09-11 09:00:00 +0900
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

### In this article, we learned how to implement Flip a String Multiple Times (with.Java).

We've been solving coding test problems, reflecting on the problems we've solved, and learning about other ways to solve them.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

A string my_string and a two-dimensional array of integers queries are given as parameters.

The elements of queries are of the form [s, e], which means to flip my_string from index s to index e.

Write a solution function to return the string after processing the commands in queries in order in my_string.

##### Example input and output

my_string: "rermgorpsam"

queries: [[2, 3], [0, 7], [5, 9], [6, 10]]

result: "programmers"

If my_string is "rermgorpsam" and the given queries are processed in order, the result is

| queries | my_string     |
| ------- | ------------- |
| [2, 3]  | "remrgorpsam" |
| [0, 7]  | "progrmersam" |
| [5, 9]  | "prograsremm" |
| [6, 10] | "programmers" |

So it returns "programmers".

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
import java.util.*;

class Solution {
    public String solution(String my_string, int[][] queries) {
        StringBuilder answer = new StringBuilder();
        ArrayList<Character> arr = new ArrayList<Character>();

        for(int k = 0; k < my_string.length(); k++) {
            arr.add(my_string.charAt(k));
        }

        for(int i = 0; i < queries.length; i++) {
            int startIndex = queries[i][0];
            int endIndex = queries[i][1];
            reverse(arr, startIndex, endIndex);
        }

        for (int l = 0; l < arr.size(); l++) {
            answer.append(arr.get(l));
        }

        } return answer.toString();
    }

    private void reverse(ArrayList<Character> arr, int startIndex, int endIndex) {
        while (startIndex < endIndex) {
            char temp = arr.get(startIndex);
            arr.set(startIndex, arr.get(endIndex));
            arr.set(endIndex, temp);
            startIndex++;
            endIndex--;
        }
    }
}
```

##### Solution

Declare a variable, answer, for string synthesis via StringBuilder.

Then declare arr to control it as a Character type, and store my_string as a char in arr, character by character.

We then execute the reverse function reverse(arr, startIndex, endIndex); passing in three arguments.

The reverse function will continue to insert values in the order of the array until startIndex is less than endIndex. To change the end and start values, we need a non-variable variable.

We declare the non-variable temp to pre-assign the start value and insert that value at endIndex.

To continue the computation, we increment startIndex by 1 and decrement endIndex by 1.

We do this all at once to cut the number of iterations in half. It then inserts the elements of arr into answer, and outputs it.

The logic is similar to mine, but there is some enlightening code out there that I'd like to review.

#### Another solution

```java
class Solution {

    char[] arr;

    public String solution(String my_string, int[][] queries) {

        arr = my_string.toCharArray();

        for (int[] query : queries) {
            reverse(query[0], query[1]);
        }

        } return new String(arr);
    }

    private void reverse(int s, int e) {
        while (s < e) {
            char temp = arr[s];
            arr[s++] = arr[e];
            arr[e--] = temp;
        }
    }
}
```

##### Explanation of the solution

This code is very similar in logic to my code. The main differences are the absence of arr in the parameters of the reverse function, void, and the increment and decrement operators on index in the array.

Let's unpack this one by one: first of all, the reverse function doesn't have arr in its parameters, so why would it be available in another function? In this code, **arr is an instance variable of the class Solution.** These instance variables are accessible from all instance methods within the class, so the reverse method has direct access to arr.

A new copy of an instance variable is created each time an object is created, and all instance methods of that object reference the same variable. Therefore, if you change the contents of arr in the reverse method, that change will also be reflected in the solution method.

Because of this property, you can access and modify arr from within the reverse method without having to pass it as a parameter. This is a common pattern in object-oriented programming, allowing methods within a class to share and manipulate the same state.

Next up is void. In Java, the void keyword is used when a particular method does not have a return value. In other words, if a method performs an action but does not return a value to the caller, you specify void as the return type in the method declaration.

Methods that use void are often used when they perform some action or change the state of an object and don't need to return the **result to the caller.**

Finally, we have the increment and decrement operators at the index positions in the array. Usually, we use increment and decrement operators by subtraction, but we don't often see increment and decrement operators at the index, so we did a little research.

++x: first increments the value of the operand by 1, then proceeds with the operation.

x++: perform the operation first, then increment the value of the operand by 1.

x --x: decrement the value of the operand by one before proceeding with the operation.

x--: Performs the operation first, then decrements the value of the operand by one.

It's important to note that these operations can also be performed on arrays. Thanks for reading.

###### Reference

**What is a StringBuilder?**

StringBuilder is a class that allows you to efficiently manipulate strings in Java. Normal string concatenation operations use String, an immutable object, which can be a performance disadvantage when many concatenation operations are required.

The traditional string concatenation method creates a new String object each time a new string is added, which can result in significant overhead if many concatenations are required.

StringBuilder, on the other hand, uses an internal buffer to manipulate strings, making string concatenation faster. Using StringBuilder can significantly improve the time complexity and space complexity of string manipulation operations.
