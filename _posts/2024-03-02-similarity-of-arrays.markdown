---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Similarity_Of_Arrays
title: Similarity of arrays (with.Java)
# title: Similarity of arrays (with.Java)
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
date: 2024-03-02 09:00:00 +0900
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

## This article examines the “Similarity of Arrays” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

I'm trying to see how similar the two arrays are.

Given string arrays s1 and s2, complete the solution function to return the same number of elements.

#### Restrictions

- 1 ≤ s1, length of s2 ≤ 100
- Length of elements of 1 ≤ s1, s2 ≤ 10
- The elements of s1 and s2 consist of only lowercase alphabet letters.
- s1 and s2 each have no duplicate elements.

#### Input/Output Example

| s1              | s2                          | result |
| --------------- | --------------------------- | ------ |
| ["a", "b", "c"] | ["com", "b", "d", "p", "c"] | 2      |
| ["n", "omg"]    | ["m", "dot"]                | 0      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public int solution(String[] s1, String[] s2) {
         int answer = 0;
         for(int i = 0; i < s1.length; i++){
             for(int j = 0; j < s2.length; j++){
                 answer += s1[i].equals(s2[j]) ? 1:0;
             }
         }
         return answer;
     }
}
```

### Solution explanation

- This method is executed by receiving two string arrays s1 and s2 as arguments.
- Inside the method, a variable called answer is initialized to 0, and a double loop is used to compare each element of the s1 array with each element of the s2 array.
- If the two strings are the same, add 1 to the answer, and if they are different, add 0.
- Finally, the value of the answer variable is returned.
- This value indicates how many values are the same in the s1 array and s2 array.
- For example, if the s1 array is ["apple", "banana", "orange"] and the s2 array is ["banana", "orange", "grape"], then the same values in the s1 and s2 arrays are " There are two in total: “banana” and “orange.”
- The solution method will return 2.
