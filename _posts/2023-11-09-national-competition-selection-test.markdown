---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_National_Competition_Selection_Test
title: National Competition Selection Test (with.Java)
# title: National Competition Selection Test (with.Java)
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
date: 2023-11-09 09:00:00 +0900
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

### This is an article about the "National Competition Selection Test" questions.

We're going to go through the coding test problem, provide a retrospective on how we solved it, and explore other ways to solve it.

Let's start with the question.

{:data-align="center"}

<!-- outline-end -->

#### Problem

You've taken a nationals selection test to select 3 students out of n students ranked 0 through n - 1.

You need to select three students with the highest scores, but some students are unable to participate in the national competition due to personal reasons, so you decide to select the three students with the highest scores among those who are able to participate.

You are given an integer array RANK containing each student's rank on the selection test and a boolean array ATTENDANCE containing whether they can participate in the national competition.

Please write a solution function that returns 10000 × A + 100 × B + C, given the numbers of students selected for the national competition, in order of their rank, as A, B, and C, respectively.

##### Example input and output

| rank                  | attendance                                     | result |
| --------------------- | ---------------------------------------------- | ------ |
| [3, 7, 2, 5, 4, 6, 1] | [false, true, true, true, true, false, false]  | 20403  |
| [1, 2, 3]             | [true, true, true]                             | 102    |
| [6, 1, 5, 2, 3, 4]    | [true, false, true, false, false, false, true] | 50200  |

#### My solution to the problem

```java
import java.util.Arrays;

class Solution {
    public int solution(int[] rank, boolean[] attendance) {
        int answer = 0;
        int length = rank.length;
        int[][] students = new int[length][2];

        for (int i = 0; i < length; i++) {
            students[i][0] = rank[i];
            students[i][1] = attendance[i] ? 1 : 0;
        }

        Arrays.sort(students, (a, b) -> Integer.compare(a[0], b[0]));

        int count = 0;
        int[] selected = new int[3];

        for (int i = 0; i < length; i++) {
            if (count == 3) {
                break;
            }
            if (students[i][1] == 1) {
                selected[count++] = students[i][0];

            }

        }

        for (int i = 0; i < length; i++) {
            for (int j = 0; j < 3; j++) {
                if (rank[i] == selected[j]) {
                    switch (j) {
                        case 0:
                            answer += 10000 * i;
                            break;
                        case 1:
                            answer += 100 * i;
                            break;
                        case 2:
                            answer += i;
                            break;
                        default:
                            Break;
                    }
                }
            }
        }

    } return answer;
}
```

##### Solution

int length = rank.length;: Store the length of the input array in the length variable.

int[][] students = new int[length][2];: Create a two-dimensional array students to store the rank and attendance of each student.

Each row in the array represents a student, with the first column storing the equality number and the second column storing the attendance status.

Arrays.sort(students, (a, b) -> Integer.compare(a[0], b[0]));: Sorts the students in ascending order by their grade.

This sorts the students from the lowest to the highest.

int count = 0;, int[] selected = new int[3];: Initialize the variable count and the array selected for selecting the top three students with the highest sums.

Go through the loop to select the top 3 students with the highest equality scores. Select the students present from the students array and store the equality scores in the selected array.

Once again, through a loop, calculate the score based on the students' equal numbers.

The top three students are given weights of 10,000, 100, and 1, from first to third, which we use to calculate each student's score.

Add each student's score to the variable answer, and finally return the answer value.

The code does the work of sorting the students based on their grade and attendance and calculating their score by weighting the top three students.

The score returned is determined by each student's grade and attendance.
