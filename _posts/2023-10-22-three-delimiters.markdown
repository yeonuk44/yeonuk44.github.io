---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Three_Delimiters
title: Three delimiters (with.Java)
# title: Three delimiters (with.Java)
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
date: 2023-10-22 09:00:00 +0900
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

### In this article, we learned how to split a string with three separators.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given an arbitrary string, we want to split the string using the letters "a", "b", and "c" as separators.

For example, if the given string is "baconlettucetomato", the list of split strings will be ["onlettu", "etom", "to"].

Given a string myStr, complete the solution function to return an array that stores the strings split using "a", "b", and "c" in order, as shown in the example above.

However, if there are no other characters between the two separators, it will store nothing, and if the array to return is empty, it will return ["EMPTY"].

##### Example input and output

| myStr                | result                    |
| -------------------- | ------------------------- |
| "baconlettucetomato" | ["onlettu", "etom", "to"] |
| "abcd"               | ["d"]                     |
| "cabab"              | ["EMPTY"]                 |

#### My solution to the problem

```java
class Solution {
    public String[] solution(String myStr) {
        StringBuilder str = new StringBuilder("");
        boolean insideWord = false;
        for(int i = 0; i < myStr.length(); i++){
            if(myStr.charAt(i) == 'a' || myStr.charAt(i) == 'b' || myStr.charAt(i) == 'c'){
                if (insideWord) {
                    str.append(' ');
                    insideWord = false;
                }
            } else{
                str.append(myStr.charAt(i));
                insideWord = true;
            }
        }
        if(str.length() == 0){
            str.append("EMPTY");
        }
        String[] answer = str.toString().split(" ");
        return answer;
    }
}
```

##### Explanation of the solution

The main logic is to iterate over the input string myStr, checking for each character, and if it encounters the characters 'a', 'b', 'c', remove them and split the word.

We use the insideWord variable to keep track of whether we are inside the current word.

Use the StringBuilder object str to dynamically build the string.

The append(char c) method of StringBuilder class: adds a character to the string builder.

toString() method of class StringBuilder: Converts a StringBuilder object to a string.

split(String regex) method of class String: Splits a string by a regular expression pattern or delimiter and returns it as an array of strings.
