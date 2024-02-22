---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Decryption
title: Decryption (with.Java)
# title: Decryption (with.Java)
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
date: 2024-02-22 09:00:00 +0900
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

## This is an article about the “decryption” problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Military strategist Murseogi discovered that the enemy used the following encryption system during the war.

Send and receive encrypted string ciphers.

In that string, only the letters that are multiples of code are the real password.

Complete the solution function to return the decrypted cipher string when the string cipher and integer code are given as parameters.

#### Restrictions

- 1 ≤ cipher length ≤ 1,000
- 1 ≤ code ≤ length of cipher
- The cipher consists only of lowercase letters and spaces.
- Spaces are also treated as one character.

#### Input/Output Example

| cipher                     | code | result     |
| -------------------------- | ---- | ---------- |
| "dfjardstddetckdaccccdegk" | 4    | "attack"   |
| "pfqallllabwaoclk"         | 2    | "fallback" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
class Solution {
     public String solution(String cipher, int code) {
         StringBuilder sb = new StringBuilder();
         int max = cipher.length() / code;
         for(int i = 1; i <= max; i++){
             int temp = i * code;
             sb.append(cipher.charAt(temp - 1));
         }
         return sb.toString();
     }
}
```

### Solution explanation

First, we create sb, a StringBuilder object. This object is used to process strings efficiently.

Next, the length of the cipher divided by the code is stored in max. This indicates the number of characters to extract.

And then iterate through the numbers from 1 to max through a for loop. This indicates the location of the character to extract.

Inside the loop, the value multiplied by i and code is stored in the temp variable. This is used to calculate the index of the character to be extracted.

And add cipher.charAt(temp - 1) to sb. The charAt method returns the character corresponding to the given index. Subtract 1 because the index of temp - 1 starts from 0, while temp starts from 1.

Finally, we call sb.toString() to convert the StringBuilder object to a string and return it.

This returns a new string containing the characters extracted at code intervals from the cipher string in order.
