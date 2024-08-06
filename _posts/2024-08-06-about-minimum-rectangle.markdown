---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Minimum_Rectangle
title: Minimum rectangle (with.Java)
# title: Minimum rectangle (with.Java)
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
date: 2024-08-06 09:00:00 +0900
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

## This is an article about the minimum rectangle (with.Java) problem.

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

The company that makes business card wallets is trying to determine the size of the wallet.

You should make a wallet that can store all business cards of various shapes and sizes and is small and easy to carry.

To create a wallet that meets these requirements, the design team examined the width and length of all business cards.

The table below shows the horizontal and vertical lengths of the four business cards.

| Business card number | Horizontal length | Vertical length |
| -------------------- | ----------------- | --------------- |
| 1                    | 60                | 50              |
| 2                    | 30                | 70              |
| 3                    | 60                | 30              |
| 4                    | 80                | 40              |

The longest horizontal and vertical lengths are 80 and 70, respectively, so if you make a wallet measuring 80 (width) x 70 (length), you can store all your business cards.

However, if you store your business card number 2 horizontally, you can store all your business cards in an 80 (horizontal) x 50 (vertical) wallet.

The wallet size at this time is 4000 (=80 x 50).

Two-dimensional array sizes representing the horizontal and vertical lengths of all business cards are given as parameters.

When you create the smallest wallet that can hold all your business cards, complete the solution function to return the size of your wallet.

#### Restrictions

- The length of the sizes is greater than 1 and less than 10,000.
- The elements in the sizes are of the [w, h] type.
- w represents the horizontal length of the business card.
- h represents the vertical length of the business card.
- W and h are natural numbers greater than 1 and less than 1,000.

#### Input/Output Examples

| sizes                                         | result    |
| --------------------------------------------- | --------- | ------- | ------ |
| [[60, 50], [30, 70], [60, 30], [80, 40]]      | 4000      |
| [[10, 7], [12, 3], [8, 15], [14, 7], [5, 15]] | 120       |
| [[14, 4], [19, 6], [6, 16], [18, 7], [7, 11]] | 133       |
| <!--                                          | start_num | end_num | result |
| ---------                                     | -------   | ------  |
| 10                                            | 3         | 0       | -->    |

### my solution to the problem

```java
class Solution {
    public int solution(int[][] sizes) {
        int answer = 0;
        int temp = 0;
        int maxRow = 0;
        int maxCol = 0;
        for(int i = 0; i < sizes.length; i++){
            temp = sizes[i][0];
            if(temp < sizes[i][1]){
                sizes[i][0] = sizes[i][1];
                sizes[i][1] = temp;
            }
            if(maxRow < sizes[i][0]){
                maxRow = sizes[i][0];
            }
            if(maxCol < sizes[i][1]){
                maxCol = sizes[i][1];
            }
        }
        answer = maxRow * maxCol;
        return answer;
    }
}
```

### Solution Description

- The solution method takes a two-dimensional integer array sizes as input.
- Initialize the variable answer, and initialize the variable maxRow, which represents the maximum horizontal length when placed horizontally, and maxCol, which represents the maximum vertical length when placed vertically.
- Use the for loop to traverse the horizontal and vertical lengths of each square.
- Compare horizontal and vertical lengths for each square, and if the width is less than vertical, exchange horizontal and vertical lengths with each other. This is to make sure that the width is always greater than or equal to vertical.
- Update the maximum horizontal and vertical lengths, which means the horizontal and vertical lengths when all squares are positioned to make the most of them.
- Finally, multiply the maximum horizontal length by the maximum vertical length and store it in answer.
  Returns answer.

### Conclusion

This code solves the problem of finding the area where the squares can be placed as wide as possible, taking into account the horizontal and vertical lengths of each square.
