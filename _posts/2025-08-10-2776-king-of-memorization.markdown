---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-2776-king-of-memorization
title: Baekjun 2776, King of memorization (with.Java)
# title: Baekjun 2776, King of memorization (with.Java)
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
date: 2025-08-10 09:00:00 +0900
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

## Baekjun No. 2776, this is an article about King of Memorization (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Yeonjong has a great memory.

So I can remember all the integers I saw during the day.

However, Dong-gyu, who cannot believe this, decides to test his memory.

Dong-gyu followed Yeonjong and wrote down all the essence he saw for a day in 'Paper 1'.

Based on that, Dong-gyu asked Yeon-jong M questions to see if he was a real memorizer.

The question is, "Have you seen the integer X today?"

Yeonjong answered all of them without being blocked, and Dong-gyu wrote down the numbers that Yeonjong claimed to have seen in 'Handbook 2'.

Back home, Dong-gyu tries to check if the answer is correct, but he is having such a hard time following Yeonjong, so he asked you for help.

To help Dong-gyu, write a program in the order written in 'Handbook 2', for each number, 1 if it is in 'Handbook 1', and 0 if it is not.

#### Input

The number of test cases T is shown in the first line.

In the next line, the number N (1 ≤ N ≤ 1,000,000) of integers written in 'Handbook 1' is input.

The next line contains N integers written in 'Handbook 1'.

The next line is given the number M (1 ≤ M ≤ 1,000,000) of integers written in 'Handbook 2', and the next line is given M integers written in 'Handbook 2'.

The range of all integers is int.

#### Output

In the order of M numbers written in 'Handbook 2', 1 is output if it is in 'Handbook 1', and 0 is output if it is not.

### problem solving

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.BufferedWriter;
import java.io.OutputStreamWriter;
import java.io.IOException;

class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        int T = Integer.valueOf(br.readLine());
        for(int i = 0; i < T; i++){
            int count = 0;
            char[] arr = br.readLine().toCharArray();
            for(char ch : arr){
                if(ch == '('){
                    count++;
                    if(count > arr.length){
                        break;
                    }
                }else{
                    count--;
                    if(count < 0){
                        break;
                    }
                }
            }
            if(count != 0){
                bw.write("NO");
                bw.newLine();
            }else{
                bw.write("YES");
                bw.newLine();
            }
        }
        br.close();
        bw.flush();
        bw.close();
    }
}
```

#### Solution Description

This code is a program that verifies that each string is correct parentheses given multiple parentheses.

Processing inputs and outputs with BufferedReader and BufferedWriter increases efficiency.

First, read the number T of test cases in the first line.

For each test case, read the parentheses string and convert it into a character array.

After that, the count is increased when the parentheses '(') are opened while traversing each character, and the count is decreased when the parentheses '(') are closed.

In this process, if the count becomes negative, it means that there are more parentheses to close than the parentheses to open, so stop repeating.

After the iteration, output "NO" if the count is not 0, and "YES" if it is 0.

This indicates whether each test case is correct parentheses or not.

Finally, after processing all inputs, the BufferedWriter outputs the results, empties and closes the buffer.

This process allows you to efficiently verify that the square bracket string is correct.
