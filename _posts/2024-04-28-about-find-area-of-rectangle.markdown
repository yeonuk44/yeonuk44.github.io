---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_Area_Of_Rectangle
title: Find the area of a rectangle (with.Java)
# title: Find the area of a rectangle (with.Java)
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
date: 2024-04-28 09:00:00 +0900
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

## This is an article about the problem of “Finding the area of a rectangle (with.Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

There is a rectangle in a two-dimensional coordinate plane whose sides are parallel to the axis.

When an array dots containing the coordinates of the four vertices of a rectangle [[x1, y1], [x2, y2], [x3, y3], [x4, y4]] is given as a parameter, the solution function returns the area of the rectangle. Try completing it.

#### Restrictions

- Length of dots = 4
- Length of element of dots = 2
- 256 < element of dots[i] < 256
- Incorrect input will not be given.

#### Input/Output Example

<!-- | array | height | result |
| -------------------- | ------ | ------ |
| [149, 180, 192, 170] | 167 | 3 |
| [180, 120, 140] | 190 | 0 | -->

| dots                                 | result |
| ------------------------------------ | ------ |
| [[1, 1], [2, 1], [2, 2], [1, 2]]     | 1      |
| [[-1, -1], [1, 1], [1, -1], [-1, 1]] | 4      |

### My solution to the problem

```java
class Solution {
     public int solution(int[][] dots) {
         int answer = 0;
         int x = dots[0][0];
         int y = dots[0][1];
         int weight = 0;
         int height = 0;

         for(int i = 1; i < dots.length; i++){
             if(x != dots[i][0]){
                 weight = Math.abs(x - dots[i][0]);
             }
             if(y != dots[i][1]){
                 height = Math.abs(y - dots[i][1]);
             }
         }

         answer = weight * height;
         return answer;
     }
}
```

### Solution explanation

- Store coordinates of first point: Stores the x and y coordinates of the first point in the given array of points in variables x and y.
- Calculation of horizontal and vertical length: Repeat from the second point to the last point to find the difference between the x and y coordinates to calculate the horizontal length width and vertical length height, respectively.
- Calculate the area of a rectangle: Multiply the horizontal length and the vertical length to find the area of the rectangle.
- Return result: Store the area of the obtained rectangle in the answer variable and return it.

**Code Advantages**

- Calculate the width and height based on the first point: Find the area of the rectangle by calculating the width and height based on the first point among the given points.
- Calculation of absolute values of horizontal and vertical lengths: Calculate the distance between two points as absolute values to obtain the horizontal and vertical lengths.

**Code Disadvantages**

- Direction of the square according to the order of the points: The direction of the square may vary depending on the order of the points, and the method of calculating the horizontal and vertical lengths may also vary accordingly. Therefore, it may not handle all cases accurately.
