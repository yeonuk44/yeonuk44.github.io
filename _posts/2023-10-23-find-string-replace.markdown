---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_String_Replace
title: Find String Replace (with.Java)
# title: Find String Replace (with.Java)
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
date: 2023-10-23 09:00:00 +0900
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

### In this article, we learned how to find the string substitution.

We'll do this by solving a coding test problem, reflecting on the problem we solved, and learning about other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

You are given two strings, myString and pat, consisting of the letters "A" and "B".

Complete a solution function that returns 1 if pat is a consecutive substring of the strings myString with "A" replaced by "B" and "B" replaced by "A" and 0 otherwise.

##### Example input and output

myString: "ABBAA"

pat: "AABB"

result: 1

#### My solution to the problem

```java
class Solution {
    public int solution(String myString, String pat) {
        int answer = 0;
        char[] ch = new char[myString.length()];
        for(int i = 0; i < myString.length(); i++){
            if(myString.charAt(i) == 'A'){
                ch[i] = 'B';
            }else{
                ch[i] = 'A';
            }
        }
        if(String.valueOf(ch).contains(pat)){
            answer = 1;
        }
        } return answer;
    }
}
```

##### solution description

public int solution(String myString, String pat):

Begins the definition of the solution method. This method accepts two string arguments, myString and pat, and returns an integer result.

int answer = 0;:

Declare a variable named answer and initialize it to 0. This variable will store the final result.

char[] ch = new char[myString.length()];:

Declare an array of characters, ch, with a length equal to the length of myString. This array will be used to transform myString.

for(int i = 0; i < myString.length(); i++):

Traverse each character in myString using a for loop.

if(myString.charAt(i) == 'A'){:

Check if the character at the current index i is 'A'.

ch[i] = 'B';:

If it is 'A', convert the character to 'B' and store it in the ch array.

}else:

If not 'A',

ch[i] = 'A';:

Convert that character to 'A' and store it in the ch array.

if(String.valueOf(ch).contains(pat)):

Convert the ch array to a string, and check if the converted string contains the string pat.

answer = 1;:

If pat is contained in ch, set answer to 1.

return answer;:

Finally, return the value of answer.

This code performs a simple string processing operation that converts myString to alternately 'A' and 'B' and then checks if it contains the string pat. The resulting value will be either 1 (contained) or 0 (not contained).
