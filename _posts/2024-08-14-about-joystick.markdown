---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Joystick
title: Joystick (with.Java)
# title: Joystick (with.Java)
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
date: 2024-08-14 09:00:00 +0900
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

## This is an article about the joystick (with.Java) problem.

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Complete the alphabet names with joysticks.

At first, it only consists of A.

ex. The name that needs to be completed is AAA if it's three letters, and AAA if it's four letters

If you move the joystick in each direction, it looks like below.

▲ - Next alphabet

▼ - Previous alphabet (move down from A to Z)

◀ - Move the cursor to the left (if you move to the left from the first position, the cursor to the last character)

▶ - Move cursor to the right (if you move to the right from the last position, cursor to the first character)

For example, you can create a "JAZ" in the following way.

- In the first position, operate the joystick up 9 times to complete J.
- Move the cursor to the last character position by manipulating the joystick to the left once.
- In the last position, operate the joystick down once to complete Z.

So you can move 11 times to make "JAZ", which is the minimum movement.

If the name you want to create is given as a parameter, create a solution function to return the minimum number of joystick operations for the name.

#### Restrictions

- The name consists only of uppercase letters.
- The length of the name is 1 or more and 20 or less.

#### Input/Output Examples

| name     | return |
| -------- | ------ |
| "JEROEN" | 56     |
| "JAN"    | 23     |

### my solution to the problem

```java
class Solution {
    public int solution(String name) {
        int answer = 0;
        int cursor = name.length() - 1;

        for(int i = 0; i < name.length(); i++){
            answer += Math.min(name.charAt(i) - 'A', 'Z' - name.charAt(i) + 1);
            if(i < name.length() - 1 && name.charAt(i + 1) == 'A'){
                int temp = i + 1;
                while(temp < name.length() && name.charAt(temp) == 'A'){
                    temp++;
                }
                cursor = Math.min(cursor, (i * 2) + (name.length() - temp));
                cursor = Math.min(cursor, i + (name.length() - temp) * 2);
            }
        }
        return answer + cursor;
    }
}
```

### Solution Description

First, the answer variable is a variable that accumulates the number of manipulations of a string that must be created by manipulating each character.

Examine each character by repeating the string from start to finish.

Choose a smaller value between the distance from the current character 'A' and the distance from the current character 'Z' to the current character to calculate the minimum number of operations required to manipulate the character.

For example, if the current character is 'B', you can manipulate 'A' up to one space, so one manipulation is required.

Alternatively, you can operate one space down from 'Y' to 'Z', so you need one operation.

In this way, each character calculates the number of operations and accumulates them in the answer variable.

Next, if you meet successive 'A', calculate the additional number of moves.

If you encounter the part leading to 'A', you should consider the additional number of operations as you move next.

This is because when you meet consecutive 'A', the number of manipulations will also occur when you go back.

Therefore, if you encounter a continuous 'A' after the current character, you calculate the number of additional operations until the next move.

Use the cursor variable for this.

The cursor variable stores the minimum number of additional operations when meeting successive 'A' and moving on.

To initialize this, initialize the cursor to the length of the name -1.

This is because we assume that one move to the end of the string is the worst case.

If you meet successive 'A', calculate the number of operations until the next move.

At this time, compare the two cases and choose a smaller value.

Move from the current character position i to the position where the successive 'A' ends, then add the distance from the end to the current position and the distance to the current position.

Alternatively, add the distance to the current position and the distance from the position where the successive 'A' ends to the end and then back again.

In this case, the distance to the current position is doubled by the distance from the position where the successive 'A' ends to the end.

Save the additional number of movements calculated in this way in the cursor variable.

Finally, add the accumulated number of text operations to the answer and the additional number of movements (cursor) to return the final number of operations.

### Conclusion

In this way, we calculate the minimum number of operations to manipulate a given string to make it a target string.
