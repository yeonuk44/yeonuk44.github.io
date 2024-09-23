---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Correct_Parentheses
title: Correct parentheses (with.Java)
# title: Correct parentheses (with.Java)
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
date: 2024-09-23 09:00:00 +0900
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

## Correct parentheses (with.J)

## I've learned about the correct parentheses (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Parentheses correctly paired means that if opened with a '(' character, it must be paired and closed with a '') character, for example

```bash
"(()" or "((())))()" is the correct parentheses.
"()()" or "(()()" is an invalid parentheses.
Given a string s consisting of only '(' or '), complete the solution function that returns true if the string s is correct parentheses and false if it is incorrect parentheses.
```

#### Restrictions

- Length of string s: natural numbers no more than 100,000
- String s consists of only '(' or '')'.

#### Input/output Examples

| s        | answer |
| -------- | ------ |
| "()()"   | true   |
| "(())()" | true   |
| ")()("   | false  |
| "(()("   | false  |

### problem solving

```java
import java.util.ArrayDeque;
import java.util.Deque;

class Solution {
    boolean solution(String s) {
        Deque<Character> deque = new ArrayDeque<>();
        for(int i = 0; i < s.length(); i++){
            deque.offer(s.charAt(i));
        }

        int count = 0;
        int size = deque.size();
        if(deque.peek() == ')' || deque.peekLast() == '('){
            return false;
        }else{
            while(!deque.isEmpty()){
                if(count < 0 || count > deque.size()){
                    return false;
                }else{
                    if(deque.poll() == '('){
                        count++;
                    }else{
                        count--;
                    }
                }
            }
        }

        return true;
    }
}
```

#### Solution Description

This code is to verify that the string s is a valid parentheses string.

A valid parentheses string must appear before the opening parentheses '(' always closing parentheses '), and the number of opening parentheses must be the same as the number of closing parentheses.

The code uses Deque to process strings and validates parentheses.

Below is a pool review that describes each part of the code.

Deque initialization and string storage:

Deque<Character> deque = new ArrayDeque<>();
Save each character in string s to Deque.

Deque is a bidirectional queue that is advantageous for character insertion and deletion.

Add string characters to Deque:

for (int i = 0; i < s.length(); i++) { deque.offer(s.charAt(i)); }
Prepare to process sequentially by adding each character in the string to Deque.

Initial condition check:

if (deque.peek() == ')' || deque.peekLast() == '(') { return false; }
If the first character of the Deque is '') or the last character is '(), return false immediately because it cannot be a valid parentheses string.

Validation of parentheses:

while (!deque.isEmpty()) { ... }
Repeat until Deque begs.

Use the count variable to balance the parentheses that you open with the parentheses that you close.

The opening parentheses '(' increase the count, and the closing parentheses '') decrease the count.

Balance check:

if (count < 0 || count > deque.size()) { return false; }
If the count is less than 0 or greater than the size of the remaining Deque, it is not a valid parentheses string.

Returns false if there are too many parentheses to open or too many parentheses to close.

Last return value:

After processing all characters, if the count is 0, return true because it is a valid parentheses string; otherwise, return false.

Problems and Improvements

Initial condition check:
Instead of using Deque to save the string and check the condition, you can check the string immediately.
