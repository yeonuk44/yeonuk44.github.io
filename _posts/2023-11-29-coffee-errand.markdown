---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Coffee_Errand
title: Coffee Errand (with.Java)
# title: Coffee Errand (with.Java)
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
date: 2023-11-29 09:00:00 +0900
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

## This is a post about the "coffee errand" problem.

We're going to take a look at solving a coding test problem, reflect on how we solved it, and learn about other ways to solve it.

Let's start with the problem.

{:data-align="center"}

<!-- outline-end -->

### The problem

Cheolsoo, the youngest member of the team, wants to buy coffee for his teammates at a café that only serves Americano and café latte.

The prices of an Americano and a café latte are 4500 and 5000 won, respectively, whether cold or hot.

Each team member is asked to write down a menu of what they would like to drink, and it is decided that those who write down only the menu will get a cold one, and those who write down "anything" will get a cold Americano.

Write a solution function that returns the amount of money to be paid at the cafe given the menu written by each employee as a string array order.

Only the following elements of order are allowed, and their meanings are given below.

Meaning of elements in order

"iceamericano", "americanoice" Cold Americano

"hotamericano", "americanohot" Hot Americano

"icecafelatte", "cafelatteice" Cold cafe latte

"hotcafelatte", "cafelattehot" hot cafe latte

"americano" Americano

"cafelatte" cafe latte

"anything" anything

#### Example input and output

| order                                                     | result |
| --------------------------------------------------------- | ------ |
| ["cafelatte", "americanoice", "hotcafelatte", "anything"] | 19000  |
| ["americanoice", "americano", "iceamericano"]             | 13500  |

My solution to the ### problem

```java
class Solution {
    public int solution(String[] order) {
        int answer = 0;
        for(String temp: order){
            if(temp.contains("americano")){
                answer += 4500;
            } else if(temp.contains("cafelatte")){
                answer += 5000;
            } else {
                answer += 4500;
            }
        }
        return answer;
    }
}
```

#### solution description

int answer = 0; : Initialize an integer variable answer to store the result.

for(String temp : order) : Iterates over the string array order, examining each order temp.

if(temp.contains("americano")) : If the order contains the string "americano":

Add 4500 to the price.

else if(temp.contains("cafelatte")) : if the order contains the string "cafelatte":

Add 5000 to the price.

else : Otherwise (if it's any other drink):

Add 4500 to the price.

return answer;: return answer after calculating the price for all orders.
