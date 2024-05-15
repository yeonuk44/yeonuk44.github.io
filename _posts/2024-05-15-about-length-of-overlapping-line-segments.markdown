---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Length_Of_Overlapping_Line_Segments
title: Length of overlapping line segments (with.Java)
# title: Length of overlapping line segments (with.Java)
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
date: 2024-05-15 09:00:00 +0900
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

## This article looks into the problem of "Length of overlapping line segments (with.Java)".

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Three line segments lie parallel.

When the two-dimensional array lines, which contains the start and end coordinates of three line segments in the form [[start, end], [start, end], [start, end]], is given as a parameter, the area where two or more line segments overlap is Complete the solution function to return the length.

The places where two or more line segments overlap are [-2, -1], [0, 1], which overlap by a length of 2.

#### Restrictions

- Length of lines = 3
- Length of elements of lines = 2
- All line segments have length 1 or more.
- The elements of lines are in the form [a, b], where a and b are each endpoint of a line segment.
- -100 ≤ a < b ≤ 100

#### Input/Output Example

<!-- | keyinput | board | result |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1] |
| ["down", "down", "down", "down", "down"] | [7, 9] | [0, -4] | -->

| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      |

### My solution to the problem

```java
class Solution {
     public int solution(int[][] lines) {
         int answer = 0;
         int[] points = new int[201];

         for(int[] line : lines){
             int start = line[0]+100;
             int end = line[1]+100;

             for(int i = start; i < end; i++){
                 points[i] += 1;
             }
         }

         for(int i : points){
             if(i > 1){
                 answer++;
             }
         }
         return answer;
     }
}
```

### Solution explanation

The answer variable is a variable that stores the number of intersection points.

Initially set to 0.

Creates an array points that represents the start and end of a line segment.

The size of this array is determined by the extent of the line segment.

Here, the range is set from -100 to 100 to represent a total of 201 points.

Iterate through the lines array to find the start and end of each line segment.

Here, each line segment is converted to an index in the points array and counted.

Increments all points through which the line segment passes by 1.

After processing all the line segments, we traverse the points array and increment the answer if the value of each point is greater than 1, which means there is a line segment that intersects at that point.

Finally, it returns the answer value.

This code allows us to efficiently calculate the number of points where line segments intersect.

The size of the array may vary depending on the range of input line segments, but this algorithm is implemented so that it can operate on any range.

What is noteworthy here is that after creating an array points to represent a line segment, the method of increasing the range of the line segment by 1 was used.

This makes it easy to calculate how many line segments each point spans.
