---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_OX_Quiz
title: OX Quiz (with.Java)
# title: OX Quiz (with.Java)
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
date: 2024-04-18 09:00:00 +0900
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

## This is an article about the "OX Quiz (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Quiz, a string array containing addition and subtraction formulas in the form of 'X [operator] Y = Z', is given as a parameter.

Complete the solution function so that it returns an array containing "O" in order if the formula is correct, and "X" if it is incorrect.

#### Restrictions

- There is always a space between the operation symbol and the number. However, there is no space between the minus sign, which indicates a negative number, and the number.
- 1 ≤ length of quiz ≤ 10
- X, Y, and Z each represent an integer consisting of numbers from 0 to 9, and there can be a minus sign at the beginning of each number, which means a negative number.
- X, Y, Z do not start with 0 except 0.
- 10,000 ≤ X, Y ≤ 10,000
- 20,000 ≤ Z ≤ 20,000
- [Operator] is either + or -.

#### Input/Output Example

| my_string                                                  | num1                 |
| ---------------------------------------------------------- | -------------------- |
| ["3 - 4 = -3", "5 + 6 = 11"]                               | ["X", "O"]           |
| ["19 - 6 = 13", "5 + 66 = 71", "5 - 15 = 63", "3 - 1 = 2"] | ["O", "O", "X", "O"] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public String[] solution(String[] quiz) {
         String[] answer = new String[quiz.length];
         String[] temp = new String[quiz.length];

         for(int i = 0; i < quiz.length; i++){
             temp = quiz[i].split(" ");

             if(temp[1].equals("+")){
                 if(Integer.valueOf(temp[0]) + Integer.valueOf(temp[2]) == Integer.valueOf(temp[4])){
                     answer[i] = "O";
                 }else{
                     answer[i] = "X";
                 }
             }

             if(temp[1].equals("-")){
                 if(Integer.valueOf(temp[0]) - Integer.valueOf(temp[2]) == Integer.valueOf(temp[4])){
                     answer[i] = "O";
                 }else{
                     answer[i] = "X";
                 }
             }
         }
         return answer;
     }
}
```

### Solution explanation

The solution method analyzes each element of the given quiz array and initializes an answer array to store the results.

We also initialize a temp array for temporary use.

We then process each element of the quiz array through a for loop.

Each element is split based on whitespace and stored in the temp array.

If the second element of the temp array is "+", convert the first and third elements to integers and check if their sum equals the fifth element.

If they are the same, "O" is stored in the corresponding index of the answer array. If they are different, "X" is stored.

If the second element of the temp array is "-", we handle it the same way.

Finally, it returns an array of answers.
