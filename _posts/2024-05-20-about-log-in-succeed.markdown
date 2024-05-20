---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Log_In_Succeed
title: log-in succeed? (with Java)
# title: log-in succeed? (with Java)
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
date: 2024-05-20 09:00:00 +0900
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

## This article looks into the "Login successful? (with. Java)" issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

I'm trying to log in to Programmers.

Given the array id_pw containing the ID and password entered by the nerd and the two-dimensional array db containing member information, complete the solution function to return a message according to login success or failure as follows.

If there is member information that matches both ID and password, "login" is returned.

When login fails, “fail” is returned if there is no member with a matching ID, and “wrong pw” is returned if there is no member with a matching ID but password.

#### Restrictions

- Members’ IDs are strings.
- Members’ IDs consist of only lowercase alphabet letters and numbers.
- Members’ passwords are strings composed of numbers.
- Members' passwords may be the same, but their IDs cannot be the same.
- The length of id_pw is 2.
- The elements of id_pw and db are in the form of [ID, password].
- 1 ≤ ID length ≤ 15
- 1 ≤ length of password ≤ 6
- length of 1 ≤ db ≤ 10
- The length of the elements of db is 2.

#### Input/Output Example

<!-- | lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| id_pw                     | db                                                                              | result     |
| ------------------------- | ------------------------------------------------------------------------------- | ---------- |
| ["meosseugi", "1234"]     | [["rardss", "123"], ["yyoom", "1234"], ["meosseugi", "1234"]]                   | "login"    |
| ["programmer01", "15789"] | [["programmer02", "111111"], ["programmer00", "134"], ["programmer01", "1145"]] | "wrong pw" |
| ["rabbit04", "98761"]     | [["jaja11", "98761"], ["krong0313", "29440"], ["rabbit00", "111333"]]           | "fail"     |

### My solution to the problem

```java
class Solution {
 public String solution(String[] id_pw, String[][] db) {
 String answer = "";
 for(int i = 0; i < db.length; i++){
 if(id_pw[0].equals(db[i][0]) && id_pw[1].equals(db[i][1])){
 return "login";
 }else if(id_pw[0].equals(db[i][0])){
 return "wrong pw";
 }else{
 answer = "fail";
 }
 }
 return answer;
 }
}
```

### Solution review

An id_pw array representing the entered ID and password and a db two-dimensional array representing database information are given.

Use a loop to iterate through each row in the database.

At each iteration, the login status is determined by checking the ID and password.

If both the ID and password match, “login” is returned and the function ends.

If the ID matches but the password does not, it returns "wrong pw" and exits the function.

The reason it immediately returns login and wrong pw and exits the function is because the problem clearly states to return immediately in the two cases. (You must read the questions carefully.)

If no matching information is found after checking all rows, returns "fail".

If no matching information is found by the time the function exits, "fail" is returned.
