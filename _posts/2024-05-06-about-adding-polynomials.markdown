---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Adding_Polynomials
title: Adding polynomials (with.Java)
# title: Adding polynomials (with.Java)
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
date: 2024-05-06 09:00:00 +0900
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

## This is an article about the "polynomial addition (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

An expression consisting of the sum of one or more terms is called a polynomial.

When calculating a polynomial, calculate and organize like terms.

When a polynomial consisting of addition is given as a parameter, complete the solution function to return the result of adding like terms as a string.

If the expressions are the same, the shortest expression is returned.

#### Restrictions

- 0 < number in polynomial < 100
- Only 'x' variable exists in polynomial.
- A polynomial consists of a positive integer, a space, ‘x’, and ‘+’.
- There is always a space between the term and the operation symbol.
- The spaces are not consecutive and there are no spaces at the beginning or end.
- There is no case where a variable comes before a number in one term.
- Invalid input such as " + 3xx + + x7 + " will not be given.
- Numbers cannot start with 0.
- Multiplication between letters and numbers is omitted.
- A polynomial has only linear terms and constant terms.
- Coefficient 1 is omitted.
- The constant term in the result is placed last.
- 0 < length of polynomial < 50

#### Input/Output Example

<!-- | keyinput | board | result |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1] |
| ["down", "down", "down", "down", "down"] | [7, 9] | [0, -4] | -->

| polynomial   | result   |
| ------------ | -------- |
| "3x + 7 + x" | "4x + 7" |
| "x + x + x"  | "3x"     |

### My solution to the problem

```java
class Solution {
 public String solution(String polynomial) {
 String answer = "";
 int xNum = 0;
 int num = 0;
 String[] strArr = polynomial.split(" ");
 for(String str : strArr){
 if(str.contains("x")){
 if(str.equals("x")){
 xNum += 1;
 }else{
 xNum += Integer.valueOf(str.replace("x", ""));
 }
 }else if(!str.equals("+")){
 num += Integer.valueOf(str);
 }
 }

 answer = (xNum != 0 ? xNum == 1 ? "x" : xNum + "x" : "") + (num != 0 ? (xNum != 0 ? " + " : "") + num : xNum == 0 ? "0" : "");
 return answer;
 }
}
```

### Solution explanation

- String separation: Separates the given polynomials based on spaces and creates a string array.
- Terms processing: A loop is executed for each term, and terms containing x and constant terms are processed separately.
- Terms containing x: Accumulate the coefficients of x, distinguishing between cases where there is only "x" and cases where a number and "x" are combined.
- Constant term: If it is not “+” and does not contain “x”, the constant term is accumulated.
- Generate result string: Generate the final result string by combining the strings for the coefficients and constant terms of x.

**Code pros and cons**

- Advantages: We implemented logic that succinctly organizes polynomials, such as calculating each term appropriately and combining the results into a string.
  The code is written to be concise and easy to understand.
- Disadvantage: This code assumes that the input fits the given format. Exception handling is required when malformed input is given.
