---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Person_Taller_Than_Shrew
title: A person taller than a shrew (with.Java)
# title: A person taller than a shrew (with.Java)
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
date: 2024-04-27 09:00:00 +0900
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

## <!-- outline-start -->

# multilingual page pair id, this must pair with translations of this page. (This name must be unique)

lng_pair: id_About_Person_Taller_Than_Shrew
title: A person taller than a shyster (with.Java)

# title: A person talking than a shrew (with.Java)

# post specific

# if not specified, .name will be used from \_data/owner/[language].yml

author: Yeonuk

# multiple categories is not supported

category: Java

# multiple tag entries are possible

tags: [java, coding test]
#thumbnailimageforpost
img: ":post_pic1.jpg"

# disable comments on this page

# comments_disable: true

# publish date

date: 2024-04-27 09:00:00 +0900
#seo

# if not specified, date will be used.

#meta_modify_date: 2021-08-10 11:32:53 +0900

# check the meta_common_description in \_data/owner/[language].yml

#meta_description: ""

#optional
#please use the "image_viewer_on" below to enable image viewer for individual pages or posts (\_posts/ or [language]/\_posts folders).

# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in \_data/conf/main.yml.

#image_viewer_on: true
#please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (\_posts/ or [language]/\_posts folders).

# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in \_data/conf/main.yml.

#image_lazy_loader_on: true

# exclude from on site search

#on_site_search_exclude: true

# exclude from search engines

#search_engine_exclude: true

# to disable this page, simply set published: false or delete this file

## #published: false

<!-- outline-start -->

## This is an article that looks into the problem of “A person who is taller than a shyster (with.Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When I was at school, I was curious about what number I should stand in line according to my height.

When an integer array containing the heights of Mushroom's classmates and the height of Mushroom's height are given as parameters, complete the solution function to return the number of people taller than Mushroom.

#### Restrictions

- 1 ≤ length of array ≤ 100
- 1 ≤ height ≤ 200
- 1 ≤ element of array ≤ 200

#### Input/Output Example

| array                | height | result |
| -------------------- | ------ | ------ |
| [149, 180, 192, 170] | 167    | 3      |
| [180, 120, 140]      | 190    | 0      |

<!-- | array | result |
| ----------- | ------ |
| [7, 77, 17] | 4 |
| [10, 29] | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(int[] array, int height) {
         int answer = 0;
         for(int x : array){
             if(x > height){
                 answer++;
             }
         }
         return answer;
     }
}

```

### Solution explanation

The element values of the array were extracted through a loop and compared with the height, which is the key of the mug.

By comparison, if there is a value greater than the height of the mush, the result is output by increasing the answer by 1.
