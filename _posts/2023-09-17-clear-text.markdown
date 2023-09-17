---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Clear_Text
title: 글자 지우기, 배열에 존재하는 값에 해당하는 인덱스를 문자열에서 지우는 방법에 대하여(with.Java)
# title: Clearing characters, how to clear the index corresponding to a value present in an array from a string (with.Java)

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
date: 2023-09-17 09:00:00 +0900
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

### Clear characters, how to clear the index corresponding to a value existing in an array from a string (with.Java)

We're going to learn by solving a coding test problem, reflecting on the problem we solved, and exploring other ways to solve it.

Let's start with the problem

{:data-align="center"}

<!-- outline-end -->

#### Problem

Given a string my_string and an array of integers indices, write a solution function that removes the characters from my_string corresponding to the elements in indices and returns the concatenated string.

##### Example input and output

my_string: "apporoograpemmemprs"

indices: [1, 16, 6, 15, 0, 10, 11, 3]

result: "programmers"

Clear the letters of the index in indices and concatenate them to get "programmers", so return that.

<!-- | i | arr[i] | stk |
| --- | ------ | ------- |
| 0 | 1 | [] |
| 1 | 4 | [1] | -->

#### My solution to the problem

```java
import java.util.*;
class Solution {
    public String solution(String my_string, int[] indices) {
        StringBuilder sb = new StringBuilder(my_string);
        Arrays.sort(indices);
        for(int i = indices.length - 1; i >= 0; i--){
           sb.deleteCharAt(indices[i]);
        }
        } return sb.toString();
    }
}
```

##### Solution.

This code deletes the character at the index corresponding to each element of the given integer array indices from the string my_string and returns the resulting string after deletion.

It creates a StringBuilder object, sb, to copy the contents of the input string, my_string. StringBuilder is an efficient class for manipulating strings.

Use Arrays.sort(indices); to sort the array of indices in ascending order. This arranges the indices to be deleted in order of lowest to highest number.

Use a loop to traverse from the last element to the first element of the indices array, that is, from high index to low index.

Delete the character at the index corresponding to indices[i] from the StringBuilder object sb by calling sb.deleteCharAt(indices[i]);. You delete from the highest index first, so the position of the preceding index is not changed.

After deleting the characters of all the indices, call sb.toString() to convert the contents of the StringBuilder object to a string and return it.

This will return a string with the characters of the indices in the indices array in my_string deleted.

###### What happens if you delete the string by index without sorting it?

I gave a little hint in the commentary, but if the leading index is pre-deleted from the string, the array will be filled with the strings remaining at the deleted index, causing the elements to swap positions and not giving the desired result.

So there you have it.
