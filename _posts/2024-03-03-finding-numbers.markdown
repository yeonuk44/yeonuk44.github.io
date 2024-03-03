---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_Numbers
title: Finding numbers (with.Java)
# title: Finding numbers (with.Java)
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
date: 2024-03-03 09:00:00 +0900
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

## This is an article about the “Find a number” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

When the integers num and k are given as parameters, if there is k among the numbers making up num, complete the solution function so that it returns the number of digits in num, and if not, it returns -1.

#### Restrictions

- 0 < num < 1,000,000
- 0 ≤ k < 10
- If there are multiple k in num, the first occurrence is returned.

#### Input/Output Example

| num    | k   | result |
| ------ | --- | ------ |
| 29183  | 1   | 3      |
| 232443 | 4   | 4      |
| 123456 | 7   | -1     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
import java.util.Arrays;

class Solution {
     public int solution(int num, int k) {
         int answer = 0;
         char[] chArr = String.valueOf(num).toCharArray();
         char chK = (char) (k + '0');

         for(int i = 0; i < chArr.length; i++){
             if(chArr[i] == chK){
                 answer = i + 1;
                 break;
             }
         }
         if(answer == 0) answer = -1;
         return answer;
     }
}
```

### Solution explanation

- Initialize the answer variable to 0. This variable serves to store the position where k first appears.
- After converting num to String, use the toCharArray() method to convert each digit into a char array.
- The value converted from k to char is stored in the chK variable.
- Use a for statement to traverse the chArr array and check if there is a number equal to chK.
- If chArr[i] and chK are the same, the value of i + 1 is stored in the answer and the loop is terminated. At this time, i + 1 means the position starting from 1.
- After the loop ends, if the answer is 0, -1 is stored because k is not in the given number.
- Finally, the answer value is returned.
