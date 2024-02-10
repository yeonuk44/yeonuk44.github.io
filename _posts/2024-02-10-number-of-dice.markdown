---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Number_Of_Dice
title: Number of dice (with.Java)
# title: Number of dice (with.Java)
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
date: 2024-02-10 09:00:00 +0900
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

## This article examines the “Number of Dice” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

I have a cuboid-shaped box and I want to fill this box with as many cube-shaped dice as possible.

When the array box, which stores the width, length, and height of the box, and the integer n, the length of the edge of the dice, are given as parameters, complete the solution function to return the maximum number of dice that can fit into the box.

#### Restrictions

- The length of the box is 3.
- box[0] = horizontal length of the box
- box[1] = vertical length of the box
- box[2] = height length of box
- 1 ≤ element of box ≤ 100
- 1 ≤ n ≤ 50
- elements of n ≤ box
- Place the dice parallel to the box.

#### Input/Output Example

| box        | n   | result |
| ---------- | --- | ------ |
| [1, 1, 1]  | 1   | 1      |
| [10, 8, 6] | 3   | 12     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int[] box, int n) {
         int answer = 0;
         int x = box[0] / n;
         int y = box[1] / n;
         int z = box[2] / n;

         answer = x * y * z;
         return answer;
     }
}
```

### Solution explanation

This problem involves calculating the volume of a box, given its size and the number to be divided.

To solve the problem, the size of the given box must be divided by each dimension (x, y, z).

You can then calculate the final volume by multiplying the divisions for each dimension.

Divide each dimension (x, y, z) of the box array by n to obtain the division value for each dimension.

Multiply the divided value to calculate the final volume.
