---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Mock_Test
title: Mock test (with.Java)
# title: Mock test (with.Java)
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
date: 2024-08-07 09:00:00 +0900
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

## This is an article about the mock test (with.Java) question.

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Spores are the abbreviations of those who gave up mathematics.

The trio of bullies are going to take all the math problems on the mock test.

The spores are taken from question 1 to the last question as follows.

- Number one: 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, ...
- Number two: 1, 2, 3, 2, 4, 5, 2, 1, 2, 3, 2, 3, 4, 5, ...
- Number three: 3, 1, 1, 2, 4, 5, 3, 1, 3, 1, 2, 4, 5, 3, 1, 2, 2, 4, 5, ...

Given an array of answers in order from question 1 to the last question, write a solution function so that the person who got the most questions right returns in the array.

#### Restrictions

- The exam consists of up to 10,000 questions.
- The answer to the question is one of 1, 2, 3, 4, and 5.
- If there are multiple people with the highest score, please sort the values that you return in ascending order.

#### Input/Output Examples

| answers     | return  |
| ----------- | ------- |
| [1,2,3,4,5] | [1]     |
| [1,3,2,4,2] | [1,2,3] |

### my solution to the problem

```java
import java.util.ArrayList;

class Solution {
    public int[] solution(int[] answers) {

        int[] person1 = {1, 2, 3, 4, 5};
        int[] person2 = {2, 1, 2, 3, 2, 4, 2, 5};
        int[] person3 = {3, 3, 1, 1, 2, 2, 4, 4, 5, 5};
        ArrayList<Integer> arr = new ArrayList<>();
        int[] count = new int[3];

        for(int i = 0; i < answers.length; i++){
            if(person1[i % person1.length] == answers[i]){
                count[0]++;
            }
            if(person2[i % person2.length] == answers[i]){
                count[1]++;
            }
            if(person3[i % person3.length] == answers[i]){
                count[2]++;
            }
        }

        int maxNum = Math.max(count[0], Math.max(count[1], count[2]));

        for(int i = 0; i < count.length; i++){
            if(maxNum == count[i]){
                arr.add(i + 1);
            }
        }

        int[] answer = new int[arr.size()];
        for(int i = 0; i < arr.size(); i++){
            answer[i] = arr.get(i);
        }
        return answer;
    }
}
```

### Solution Description

- The solution method takes an integer array answer as input.
- Save the stamping patterns of the three spores in person1, person2, and person3 arrays, respectively.
- Create an array count to store the number of problems that each blister got right. Size is 3.
- Use the for loop to traverse the array of correct answers and count the number of correct questions compared to each blister's pattern.
- Find the maximum value of the number of problems that each spore answered correctly.
- Save the number of the spores with the same value as the maximum value in the arr list.
- Returns the contents of the arr list by converting them into arrays.

### Conclusion

This code solves the problem of finding the person who got the most correct answers compared to the correct answers based on the stamping pattern of each blimp.
