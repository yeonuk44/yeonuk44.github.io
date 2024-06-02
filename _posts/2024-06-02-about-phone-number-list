---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Phone_Number_List
title: Phone number list (with.Java)
# title: Phone number list (with.Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, hash]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-06-02 09:00:00 +0900
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

## This is an article about the "Phone number list (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

I want to check if one of the phone numbers listed in the phone book is a prefix for another number.

If the phone number is as follows, the rescue team's phone number is the prefix of Youngseok's phone number.

- Rescue team: 119
- Park Jun-young: 97 674 223
- Ji Young-seok: 11 9552 4421

When phone_book, an array containing phone numbers written in the phone book, is given as a parameter to the solution function, write the solution function to return false if one number is a prefix of another number, and true otherwise.

#### Restrictions

- The length of phone_book must be between 1 and 1,000,000.
- The length of each phone number must be between 1 and 20.
- The same phone number is not included repeatedly.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| phone_book                        | return |
| --------------------------------- | ------ |
| ["119", "97674223", "1195524421"] | false  |
| ["123", "456","789"]              | true   |
| ["12", "123","1235","567","88"]   | false  |

### My solution to the problem

```java
import java.util.*;

class Solution {
 public boolean solution(String[] phoneBook) {
 Map<String, Integer> map = new HashMap<>();

 for (int i = 0; i < phoneBook.length; i++){
 map.put(phoneBook[i], i);
 }

 for (int i = 0; i < phoneBook.length; i++){
 for (int j = 0; j < phoneBook[i].length(); j++){
 if (map.containsKey(phoneBook[i].substring(0, j))){
 return false;
 }
 }
 }

 return true;
 }
}
```

### Solved review

The solution method takes as input a string array phoneBook.

Creates a Map<String, Integer> object map.

This map has each phone number as a key and the index of that phone number as a value.

The first for loop traverses the phone book and adds each phone number to the map. Use the phone number as the key and the index as the value.

A second for loop generates each phone number's prefix one by one and checks whether it is in the map.

Use phoneBook[i].substring(0, j) to create a substring from the beginning to the jth character of the current phone number.

It checks if this substring is in the map and returns false because a duplicate prefix exists.

Returns true if there are no duplicate prefixes for all phone numbers.

Let's solve it as an array as well.

#### My solution to the problem

```java
import java.util.*;

class Solution {
 public boolean solution(String[] phoneBook) {
 boolean answer = true;
 Arrays.sort(phoneBook);

 for (int i = 0; i < phoneBook.length - 1; i++){
 if (phoneBook[i + 1].startsWith(phoneBook[i])){
 answer = false;
 }
 }

 return answer;
 }
}
```

##### Solved review

The solution method takes as input a string array phoneBook.

Initialize the answer variable and set its initial value to true.

This variable will change to false if there is a number with a prefix relationship.

Sort the phone book lexicographically using Arrays.sort(phoneBook). By doing this, numbers with a prefix relationship become adjacent.

Compare adjacent phone numbers through a for loop.

Compare phoneBook[i] and phoneBook[i + 1] and change the answer to false if the former is a prefix of the latter, i.e. phoneBook[i + 1] starts with phoneBook[i].

Finally, it returns the answer value.
