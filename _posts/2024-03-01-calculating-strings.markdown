---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Calculating_Strings
title: Calculating strings (with.Java)
# title: Calculating strings (with.Java)
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
date: 2024-03-01 09:00:00 +0900
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

## This is an article about the problem of "Calculating strings".

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

my_string is a string formula, such as "3 + 5".

When the string my_string is given as a parameter, complete the solution function that returns the value calculated by the formula.

#### Restrictions

- There are only + and - operators.
- There are no spaces at the beginning or end of the string.
- Numbers starting with 0 are not given.
- Invalid formulas are not given.
- 5 ≤ length of my_string ≤ 100
- The result of calculating my_string is between 1 and 100,000.
- The median calculated value of my_string is between -100,000 and 100,000.
- The numbers used in calculations are natural numbers between 1 and 20,000.
- my_string contains at least one operator.
- The return type is an integer type.
- The numbers and operators in my_string are separated by a single space.

#### Input/Output Example

| my_string | result |
| --------- | ------ |
| "3 + 4"   | 7      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(String my_string) {
         String[] strArr = my_string.split(" ");
         int answer = Integer.parseInt(strArr[0]);

         for(int i = 0; i < strArr.length - 1; i++){
             if(strArr[i].equals("+")){
                 answer += Integer.parseInt(strArr[i + 1]);
             }else if(strArr[i].equals("-")){
                 answer -= Integer.parseInt(strArr[i + 1]);
             }
         }
         return answer;
     }
}
```

### Solution explanation

- The function receives a string as input, separates the string based on spaces, then converts the first value to an integer and sets it as the initial value. Then, through a loop, operators and operands are checked and calculations are performed.
- If it is the “+” operator, it adds the next value to the current value.
- If it is the "-" operator, the next value is subtracted from the current value.
- Returns the final calculated result.
- This code can be used as a calculator function to perform simple arithmetic operations. For example, if you enter a string like "10 + 5 - 3", the result will be 10 + 5 - 3 = 12.
- One thing to note is that there is no logic to verify that the input string is in a valid format, so unexpected behavior may occur if incorrect input is given.
