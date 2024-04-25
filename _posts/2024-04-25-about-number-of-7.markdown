---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Of_7
title: Number of 7 (with.Java)
# title: Number of 7 (with.Java)
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
date: 2024-04-25 09:00:00 +0900
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

## This is an article about the "Number of 7 (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

My favorite lucky number is 7.

When an integer array array is given as a parameter, complete the solution function to return the total number of 7s.

#### Restrictions

- 1 ≤ length of array ≤ 100
- 0 ≤ elements of array ≤ 100,000

#### Input/Output Example

<!-- | my_str | n | result |
| ------------------ | --- | ---------------------------- |
| "abc1Addfggg4556b" | 6 | ["abc1Ad", "dfggg4", "556b"] |
| "abcdef123" | 3 | ["abc", "def", "123"] | -->

| array       | result |
| ----------- | ------ |
| [7, 77, 17] | 4      |
| [10, 29]    | 0      |

### My solution to the problem

```java
class Solution {
     public int solution(int[] array) {
         int answer = 0;
         for(int i = 0; i < array.length; i++){
             String str = String.valueOf(array[i]);
             char[] chArr = str.toCharArray();
             for(char ch : chArr){
                 if(ch == '7'){
                     answer += 1;
                 }
             }
         }
         return answer;
     }
}
```

### Solution explanation

1. `public int solution(int[] array)`: The solution method is a method that takes an int array as input and returns the number of 7.
2. `int answer = 0;` : Declare the answer variable and initialize it to 0. This variable is a variable that will store the number of 7.
3. `for(int i = 0; i < array.length; i++)`: This is a loop that repeats the length of the array. It is used to check all the elements in an array one by one.
4. `String str = String.valueOf(array[i]);`: Converts the elements of the array to a string. The reason for converting an element of an array to a string is to check if that number is 7.
5. `char[] chArr = str.toCharArray();`: Converts a string to a character array. The reason for this conversion is to loop through the strings one by one and check whether it is 7.
6. `for(char ch : chArr)`: It is a loop statement that checks all elements of a character array one by one.
7. `if(ch == '7')`: Checks whether the character currently being checked is 7.
8. `answer += 1;`: If the character is 7, 1 is added to the answer variable. That is, increase the number of 7 by 1.
9. `return answer;`: After the loop ends, returns the answer variable that stores the number of 7.

The code implemented in this way performs the function of counting the number of 7s in the given array.
