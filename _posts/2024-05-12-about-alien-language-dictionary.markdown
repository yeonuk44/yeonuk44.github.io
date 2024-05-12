---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Alien_Language_Dictionary
title: Alien language dictionary (with.Java)
# title: Alien language dictionary (with.Java)
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
date: 2024-05-12 09:00:00 +0900
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

## This article looks into the issue of “Alien language dictionary (with.Java)”.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

PROGRAMMERS-962 An astronaut who crash-lands on a planet is trying to study the language of an alien planet.

An array containing the alphabet spell and an alien language dictionary dic are given as parameters.

Complete the solution function so that it returns 1 if a word that uses all of the alphabets contained in spell only once exists in dic, and returns 2 if it does not exist.

#### Restrictions

- The elements of spell and dic consist of only lowercase alphabet letters.
- 2 ≤ spell size ≤ 10
- The length of the spell element is 1.
- 1 ≤ size of dic ≤ 10
- 1 ≤ length of element of dic ≤ 10
- You must create a word using all the elements of the spell.
- There are no more than two words in the dic that can be created using all the elements of a spell.
- Neither dic nor spell have duplicate elements.

#### Input/Output Example

<!-- | keyinput | board | result |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1] |
| ["down", "down", "down", "down", "down"] | [7, 9] | [0, -4] | -->

| spell                | dic                                     | result |
| -------------------- | --------------------------------------- | ------ |
| ["p", "o", "s"]      | ["sod", "eocd", "qixm", "adio", "soo"]  | 2      |
| ["z", "d", "x"]      | ["def", "dww", "dzx", "loveaw"]         | 1      |
| ["s", "o", "m", "d"] | ["moos", "dzx", "smm", "sunmmo", "som"] | 2      |

### My solution to the problem

```java
class Solution {
     public int solution(String[] spell, String[] dic) {
         int answer = 2;
         int count = 0;
         for(String word : dic){
             for(String str : spell){
                 if(word.contains(str)){
                     count++;
                 }
             }
             System.out.println(count);
             if(count == spell.length){
                 answer = 1;
                 break;
             }else{
                 count = 0;
             }
         }
         return answer;
     }
}
```

### Solution explanation

Set the answer variable to the initial value of 2.

This variable represents the result. 2 is set as the default.

Set the count variable to an initial value of 0.

This variable is used to count the number of words included in the dic array among the words in the spell array.

Each word in the dic array is compared with the word (str) in the spell array.

If word contains str, increment the count variable.
Prints the count variable.

If the count variable is equal to the length of the spell array, it means that all words are included in the dic array, so we set the answer variable to 1 and end the loop.

Otherwise, we initialize the count variable to 0.

When all loops are completed, the answer variable is returned.

- Advantage: Performs the function of checking whether all words in a given spell array are included in the dic array. The code is concise and easy to understand. It is implemented by counting the number of matching words using the count variable.
- Disadvantage: Efficiency may be low because nested loops are used to compare words in all spells and dics. Time complexity may increase. If there are duplicate spell words, the count variable may be incremented and output incorrect results. Printing intermediate results using System.out.println(count) appears to be used for debugging purposes. In reality, it shouldn't affect the results.
- Improvement: Instead of nested loops, you can use the Set data structure to remove duplicates and find matching words. This improves efficiency. Instead of a count variable, you can use a HashSet to store the matching words, and ultimately determine the result by comparing the number of stored words with the length of the spell array. The output statement for debugging (System.out.println(count)) can be removed or used in an improved form.
