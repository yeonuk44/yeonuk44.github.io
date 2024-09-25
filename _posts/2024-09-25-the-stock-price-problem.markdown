---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Stock_Price_Problem
title: Stock price (with.Java)
# title: Stock price (with.Java)
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
date: 2024-09-25 09:00:00 +0900
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

## This is a story about the price of shares (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Complete the solution function so that when given as a parameter an array of prices containing stock prices recorded in seconds, the number of seconds the price has not dropped.

#### Restrictions

- Each price of the prices is a natural number of 1 or more and 10,000 or less.
- The length of the prices is not less than 2 but not more than 100,000.

#### Input/output Examples

| prices          | return          |
| --------------- | --------------- |
| [1, 2, 3, 2, 3] | [4, 3, 1, 1, 0] |

<!-- | priorities         | location | return |
| ------------------ | -------- | ------ |
| [2, 1, 3, 2]       | 2        | 1      |
| [1, 1, 9, 1, 1, 1] | 0        | 5      | -->

### problem solving

```java
class Solution {
    public int[] solution(int[] prices) {
        int[] answer = new int[prices.length];
        for(int i = 0; i < prices.length - 1; i++){
            int init_0 = prices[i];
            int sec = 0;

            for(int j = i + 1; j < prices.length; j++){
                int init_1 = prices[j];
                sec++;

                if(init_0 > init_1){
                    break;
                }
            }

            answer[i] = sec;
        }
        return answer;
    }
}
```

#### Solution Description

This code solves the problem of receiving an array of stock prices and calculating how many seconds each stock price has not dropped.

First, create an array to store the time when the stock price has not fallen.

The length of this array is the same as the input array.

Check the price of each stock through the first iteration.

The last stock price does not need to be compared, so repeat by subtracting one from the length of the stock array.

It stores the current stock price in a variable and initializes the variable to store the time when the stock price has not fallen.

Check the stock prices after the current stock price through the second iteration.

Store the stock price to compare in a variable and increase the time by one second because the stock price has not fallen.

If the current stock price is greater than the stock price to be compared, the stock price has fallen, so we end the iteration.

Saves the time when the current stock price has not fallen into the array.

This process calculates the amount of time that has not fallen for all stock prices, and then returns the array of results.

For example, if the stock price arrangement is 1, 2, 3, 2, 3, the first price 1 is 4 seconds without dropping, the second price 2 is 3 seconds, the third price 3 is 1 second, the fourth price 2 is 1 second, and the last price 3 is 0 seconds because there is no need to compare.

So the resulting array is 4, 3, 1, 1, 0.

This code solves the problem of efficiently calculating the time when stock prices have not fallen and returning them in array form.
