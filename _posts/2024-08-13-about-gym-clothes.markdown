---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Gym_Clothes
title: gym clothes (with.Java)
# title: gym clothes (with.Java)
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
date: 2024-08-13 09:00:00 +0900
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

## This is an article about the issue of sportswear (with.Java).

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Some students had their gym clothes stolen because they were robbed at lunchtime.

Fortunately, a student with extra gym clothes is trying to lend them their gym clothes.

Students' numbers are arranged in order of physique, so you can only lend your gym clothes to the students in the front number or the students in the back number.

For example, student number 4 can only lend their gym clothes to student number 3 or student number 5.

    Since you can't take classes without gym clothes, you should borrow gym clothes properly and take as many students as possible.

Write a solution function to return the maximum value of students who can take PE classes, given the number n of students whose PE uniforms are stolen, the array lost with the number of students who brought extra PE, and the array reserve with the number of students who can take PE classes as parameters.

#### Restrictions

- The total number of students is 2 or more and 30 or less.
- The number of students whose gym clothes were stolen is more than 1 and no more than n, and there are no duplicate numbers.
- The number of students who brought extra gym clothes is more than 1 and no more than n, and there are no duplicate numbers.
- Only students with extra gym clothes can lend gym clothes to other students.
- A student who brought extra gym clothes may have had their gym clothes stolen. At this time, the student assumes that only one gym clothes was stolen, and he cannot lend it to another student because he has only one gym clothes left.

#### Input/Output Examples

| n   | lost   | reserve   | return |
| --- | ------ | --------- | ------ |
| 5   | [2, 4] | [1, 3, 5] | 5      |
| 5   | [2, 4] | [3]       | 4      |
| 3   | [3]    | [1]       | 2      |

### my solution to the problem

```java
import java.util.Arrays;

class Solution {
    public int solution(int n, int[] lost, int[] reserve) {
        int answer = 0;
        Arrays.sort(reserve);
        Arrays.sort(lost);

        answer = n - lost.length;

        for (int i = 0; i < lost.length; i++) {
			for (int j = 0; j < reserve.length; j++) {
				if (lost[i] == reserve[j]) {
					answer++;
					lost[i] = -1;
					reserve[j] = -1;
                    break;
				}
			}
		}
        for(int num : lost){
            for (int j = 0; j < reserve.length; j++) {
				if (num - 1 == reserve[j] || num + 1 == reserve[j]) {
					answer++;
					reserve[j] = -1;
					break;
				}
			}
        }

        return answer;
    }
}
```

### Solution Description

First, arrange the arrangement of students who brought extra gym clothes and the stolen students.

This is to proceed more efficiently during the subsequent comparison process.

Sets the total number of students to an initial value, excluding the number of stolen students.

For now, the number of stolen students is subtracted from the total number of students, in consideration of the case where the student who brought the extra gym clothes can lend them to the stolen student.

Find the case where the stolen student and the student who brought the extra gym clothes are the same number and deal with them.

These students can take PE classes because the stolen student has lost his or her gym clothes, but he or she has brought extra gym clothes.

In this case, add those students to the total number of students excluding the number of stolen students.

Processed students will change their numbers to -1 to avoid overlapping considerations in the next navigation.

Explore if you can lend your gym clothes, considering that the distance between the students who brought extra gym clothes and the students who were stolen is 1.

If the distance between the students who brought extra gym clothes and the stolen students is 1, you can lend them to each other.

In this case, it adds to the total number of students excluding the number of stolen students.

Processed students will change their numbers to -1 to avoid overlapping considerations in the next navigation.

The total number of students, excluding the last stolen students, is the number of students who can take PE classes. Returns this value.

The code explores the cases in which students can take PE classes according to the conditions given through two iterations, and returns the number.

### Conclusion

The above code implements a process to explore the relationship between students who were stolen and those who brought extra gym clothes under several conditions.

The course is designed in detail to meet the conditions of the given problem, first processing if the stolen and the student who brought the extra gym clothes are the same number, then checking if the distance between the students who brought the extra gym clothes and the stolen students is one.
