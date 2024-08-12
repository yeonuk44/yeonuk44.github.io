---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Vowel_Dictionary
title: Vowel dictionary (with.Java)
# title: Vowel dictionary (with.Java)
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
date: 2024-08-12 09:00:00 +0900
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

## This is an article about the vowel dictionary (with.Java) problem.

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

The dictionary contains all words less than 5 in length that can be made using only the alphabetic vowels 'A', 'E', 'I', 'O', and 'U'.

In the dictionary, the first word is "A", then "AA", and the last word is "UUUUUU".

When a word is given as a parameter, complete the solution function so that it returns the number of words in the dictionary.

#### Restrictions

- The length of the word is 1 or more and 5 or less.
- The word only consists of the uppercase letters 'A', 'E', 'I', 'O', and 'U'.

#### Input/Output Examples

| word    | result |
| ------- | ------ |
| "AAAAE" | 6      |
| "AAAE"  | 10     |
| "I"     | 1563   |
| "EIO"   | 1189   |

### my solution to the problem

```java
import java.util.ArrayList;

class Solution {
    static ArrayList<String> list;
    static String[] words = {"A", "E", "I", "O", "U"};

    public int solution(String word) {
        int answer = 0;
        list = new ArrayList<>();

        dfs("", 0);
        int size = list.size();

        for (int i = 0; i < size; i++) {
            if (list.get(i).equals(word)) {
                answer = i;
                break;
            }
        }

        return answer;
    }

    static void dfs(String str, int len) {
        list.add(str);
        if (len == 5) return;

        for (int i = 0; i < 5; i++) {
            dfs(str + words[i], len + 1);
        }
    }
}
```

### Solution Description

- word: the string you want to find
- answer: a variable that stores the result
- After generating all combinations of words, see how many times the given string comes out and return it.
- Generating words with DFS navigation
- Generates all combinations of words through the dfs method.
- Add each vowel to the current string str to generate the next level of string.
- Create all combinations through the DFS navigation and store them in the list.
- Check the number of times the given string comes out
- Check all the generated combinations and return the index if it matches the given string.

### Conclusion

In this way, the code generates all combinations of words made up of a given collection through DFS navigation, and finds the number of times the given string comes out.
