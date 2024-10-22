---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Word_Transformation
title: Word Transformation (with.Java)
# title: Word Transformation (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, bfs]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-18 09:00:00 +0900
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

## I learned about word conversion (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

There are two words begin, target, and word sets.

I want to find the shortest conversion process to convert from begin to target using the following rules.

1. You can only change one alphabet at a time.
2. You can only convert to words in words. For example, if begin is "hit", target is "cog", words are ["hot", "dot", "lot", "log", "cog"] you can convert it in four steps, such as "hit" -> "hot" -> "dot" -> "dog" -> "cog".

When two words begin, target, and word set words are given as parameters, write a solution function so that at least a few steps can be taken to return the begin to target.

#### Restrictions

- Each word consists of only lowercase alphabetic characters.
- Each word has a length of not less than 3 and not more than 10, and all words have the same length.
- Words have more than 3 words and no more than 50 words and no words are duplicated.
- Begin and target are not the same.
- If the conversion is not possible, return 0.

#### Input/output Examples

<!-- | operations                                                                  | return     |
| --------------------------------------------------------------------------- | ---------- |
| ["I 16", "I -5643", "D -1", "D 1", "D 1", "I 123", "D -1"]                  | [0,0]      |
| ["I -45", "I 653", "D 1", "I -642", "I 45", "I 97", "D 1", "D -1", "I 333"] | [333, -45] | -->

| begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      |

### problem solving

```java
import java.util.Queue;
import java.util.LinkedList;
import java.util.ArrayList;

class Solution {
    public int solution(String begin, String target, String[] words) {
        int answer = 0;
        Queue<String> que = new LinkedList<>();
        ArrayList<String> list = new ArrayList<>();
        int check = 0;
        for(String str : words){
            list.add(str);
        }
        if(!list.contains(target)){
            return 0;
        }

        que.offer(begin);
        list.remove(begin);

        while(!que.isEmpty()){
            for(int i = 0; i < que.size(); i++){
                String temp = "";
                String current_str = que.poll();
                if(current_str.equals(target)){
                    return answer;
                }
                for(String str : list){
                     if(convert(current_str, str)){
                         que.offer(str);
                         temp = str;
                     }
                }
                list.remove(temp);
            }
            answer++;
        }

        return 0;
    }

    public boolean convert(String word_1, String word_2){
        int count = 0;
        for(int i = 0; i < word_1.length(); i++){
            if(word_1.charAt(i) != word_2.charAt(i)){
                count++;
            }
        }

        return count == 1;
    }
}
```

#### Solution Description

The given problem is to obtain the minimum number of conversions to convert from the start string begin to the target string target.

However, during the transformation process, each word must exist in a list of words given in advance, and each word can only change one character at a time.

Implement BFS using Queue and ArrayList to resolve the issue.

Use BFS to find the shortest path from the begin string to the target string.

At each transformation step, check if the current word and the next word differ by only one letter.

Verify that the target word target has been reached during the conversion process.

During the initialization phase, the queue <String> queue is used as a queue to implement BFS, and the ArrayList <String> list stores a list of convertible words.

The answer variable is used to store the number of transformations. Transform the words array to list and make sure the target word is in the list.

If the target is not listed, return 0 because it cannot be converted.

In the BFS navigation process, you add the start word begin to the queue and remove it from the list.

Repeat until the queue begs to explore all words at each level.

Find and add the current and transformable words to the queue. Transformed words are removed from the list to prevent duplicate searches.

Returns the number of transformations when the target word is reached.

The convert method checks if two words differ by only one letter.

If the difference is 1 by comparing each character of the two words, return true because it can be transformed.

##### Conclusion

Within a given constraint, the minimum number of conversions from the starting string to the target string can be effectively found via BFS.

In this process, we examine the transformability and manage the transformed words to explore the optimal path.
