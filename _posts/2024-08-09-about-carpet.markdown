---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Carpet
title: Carpet (with.Java)
# title: Carpet (with.Java)
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
date: 2024-08-09 09:00:00 +0900
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

## This is an article about the carpet (with.Java) problem.

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Leo went to buy a carpet and saw a plaid carpet painted yellow in the center and brown in the rim line as shown below.

Leo returned home and remembered the number of yellow and brown colored grids on the carpet he had seen earlier, but not the size of the entire carpet.

Write a solution function so that Leo returns the horizontal and vertical sizes of the carpets in order when the number of brown grids and the number of yellow grids are given as parameters in this carpet.

#### Restrictions

- The number of brown grids is a natural number greater than 8 and less than 5,000.
- The number of yellow grids is a natural number greater than 1 and less than 2,000,000.
- The width of the carpet is equal to or longer than the length.

#### Input/Output Examples

| brown | yellow | return |
| ----- | ------ | ------ |
| 10    | 2      | [4, 3] |
| 8     | 1      | [3, 3] |
| 24    | 24     | [8, 6] |

### my solution to the problem

```java
class Solution {
    public int[] solution(int brown, int yellow) {
        int[] answer = new int[2];
        int length = brown / 2 + 1;
        int x = length;
        for(int y = 1; y < length; y++){
            if(x * y - brown == yellow){
                answer[0] = x;
                answer[1] = y;
                break;
            }
            x--;
        }
        return answer;
    }
}
```

### Solution Description

- The solution method takes the integer brown and yellow as inputs.
- The answer array will store the width and length of the rectangle.
- The length variable stores the horizontal length of the rectangle estimated by the number of brown tiles.
- Assign a horizontal length to x.
- Use the for loop to navigate the length from 1 to length.
- If the value obtained by multiplying each x and y by subtracting the number of brown tiles from the total number of tiles matches the number of yellow tiles, save the corresponding x and y values in the answer array and end the loop.
- If there are no x and y that satisfy the condition, reduce x and check the condition again.
  Finally returns the answer array.
- This code addresses the issue of returning horizontal and vertical lengths when a rectangle can be created using the number of brown and yellow tiles.

To supplement the commentary, the code follows the following logic.

- First, to find the horizontal length of a rectangle, add 1 to the number of brown tiles divided by 2. (Since brown tiles fill two horizontal and vertical lines of a rectangle, the horizontal length must be greater than or equal to the vertical length.)
- Verify that the result of subtracting the number of brown tiles from the value multiplied by the horizontal length x and the vertical length y matches the number of yellow tiles.
- If it matches, save the corresponding horizontal length x and vertical length y in the answer array and end the iteration.
- Otherwise, check again, decreasing the horizontal length x one by one.
- Finally, return the answer array.

### Conclusion

This code uses iterations to search for horizontal and vertical lengths x and y to find out if the conditions given in the problem are met, and it is stored in the answer array to return them.
