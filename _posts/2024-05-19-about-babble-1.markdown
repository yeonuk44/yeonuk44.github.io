---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Babble_1
title: Babble 1 (with.Java)
# title: Babble 1 (with.Java)
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
date: 2024-05-19 09:00:00 +0900
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

## This is an article about the "Babbling 1 (with.Java)" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to get to know myself.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Museok is taking care of his 6-month-old nephew.

My nephew can only pronounce the four sounds "aya", "ye", "woo", and "ma" using them at most once.

When the string array babbling is given as a parameter, complete the solution function so that it returns the number of words that the babbling nephew can pronounce.

#### Restrictions

- 1 ≤ length of babbling ≤ 100
- 1 ≤ length of babbling[i] ≤ 15
- In each string of babbling, “aya”, “ye”, “woo”, and “ma” each appear at most once.
- That is, among all possible substrings of each string, "aya", "ye", "woo", and "ma" occur only once.
- The string consists of only lowercase alphabet letters.

#### Input/Output Example

<!-- | lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| babbling                                    | result |
| ------------------------------------------- | ------ |
| ["aya", "yee", "u", "maa", "wyeoo"]         | 1      |
| ["ayaye", "uuuma", "ye", "yemawoo", "ayaa"] | 3      |

### My solution to the problem

```java
class Solution {
 public int solution(String[] babbling) {
 int answer = 0;
 String[] vaildBabblings = {"aya", "ye", "woo", "ma"};

 for(String sound: babbling){
 for(String validBabbling : validBabblings){
 sound = sound.replace(validBabbling," ");
 }

 sound = sound.replace(" ","");

 if(sound.equals("")){
 answer++;
 }
 }
 return answer;
 }
}
```

### Solution review

First, an array vaildBabblings is declared, which stores valid syllable combinations.

Use a double loop to remove valid syllable combinations from each string (sound).

The outer loop repeats the input string array (babbling), and the inner loop repeats valid syllable combinations.

Replaces each valid syllable combination with a space in the string.

After removing all valid syllable combinations, we remove spaces from the string.

Increment answer only if the string with all spaces removed is an empty string ("").

Finally, it returns an answer.

This code provides a simple way to find and count valid syllable combinations in an input string.
