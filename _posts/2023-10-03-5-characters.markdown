---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_5_Characters
title: How to truncate a given list of strings by 5 characters, collecting only the first character and outputting it to an array.
# title: How to truncate a given list of strings by 5 characters, collecting only the first character and outputting it to an array.

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
date: 2023-10-03 09:00:00 +0900
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

### In this article, we've learned how to take a list of strings, break them up by 5 characters, collect the first character and output them to an array (with.Java).

We'll do this by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Complete the solution function so that, given a string list names containing the names of people in line to ride a ride that holds up to 5 people, it returns a list containing the names of the people standing at the front of the group of 5 people from the front.

Include the name of the person at the front even if the last group is not five people.

##### Example input and output

names: ["nami", "ahri", "jayce", "garen", "ivern", "vex", "jinx"]

result: ["nami", "vex"]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

#### My solution to the problem

```java
class Solution {
    public String[] solution(String[] names) {
        String[] answer = new String[(int)Math.ceil(names.length / 5.0)];
        int count = 0;
        for(int i = 0; i < names.length; i += 5){
            answer[count++] = names[i];
        }
        } return answer;
    }
}
```

##### Solution

The return type of the function is String[], and it takes an array of strings called names as an argument.

The variable count is used to put the value in the answer array. Note that in Java, division between integers may not give the expected result because the result is returned as an integer and the decimal part is discarded.

That's why when we count the number of groups, we need to divide by a real number to get the correct value, which is why we've rounded it up to 5.0.

We process each group through a loop. The variable i represents the starting index of the current group, and the variable groupSize determines the size of the current group.

We add the names of the people in the group to groupNames. Find the index of the actual people and get their names via i + j.

Make each group's name into a single string and store it in the answer array. Remove leading and trailing spaces from the string and save it.

Return the completed ANSWER array and provide it as the result of the function.
