---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Prime_Factorization
title: Prime factorization (Java, HashSet, ArrayList, Set, List)
# title: Prime factorization (Java, HashSet, ArrayList, Set, List)
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
date: 2024-02-15 09:00:00 +0900
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

## This is an article about the "prime factorization" problem.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

Prime factorization is expressing a number as a product of prime numbers.

For example, the prime factorization of 12 can be expressed as 2 _ 2 _ 3.

So the prime factors of 12 are 2 and 3.

When a natural number n is given as a parameter, complete the solution function so that it returns an array containing the prime factors of n in ascending order.

#### Restrictions

- 2 ≤ n ≤ 10,000

#### Input/Output Example

| n   | result       |
| --- | ------------ |
| 12  | [2, 3]       |
| 17  | [ 17 ]       |
| 420 | [2, 3, 5, 7] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10 | 3 | 0 | -->

### My solution to the problem

```java
import java.util.*;

class Solution {
     public int[] solution(int n) {
         List<Integer> factors = new ArrayList<>();

         for (int i = 2; i <= n; i++) {
             while (n % i == 0) {
                 factors.add(i);
                 n /= i;
             }
         }

         Set<Integer> set = new HashSet<>();

         List<Integer> result = new ArrayList<>();

         for (int element : factors) {
             if (set.add(element)) {
                 result.add(element);
             }
         }

         int[] answer = new int[result.size()];
         for (int i = 0; i < result.size(); i++) {
             answer[i] = result.get(i);
         }

         return answer;
     }
}
```

### Solution explanation

- List<Integer> factors: A list that stores prime factors. Find the prime factors that can divide the given number n, starting from 2, and add them to the list.
- Set<Integer> set: HashSet to exclude duplicate prime factors. Used to prevent duplication.
- List<Integer> result: List to save excluding duplicate prime factors.
- Prime factorization: Find the prime factors that can divide the given number n starting from 2 through the for statement, add the corresponding prime factors to the factors list, and update n.
- Excluding duplicate prime factors: Use set to exclude duplicate prime factors and add unique prime factors to the result list.
- Conversion to array: Converts the result list to an array and returns it as the final result, an answer.

**Code Advantages**

- Using HashSet: You can simply remove duplicates by using HashSet to exclude duplicate prime factors.
- List utilization: List was effectively used to find prime factors and save the results excluding duplicate prime factors.

**Code Disadvantages**

- List conversion: The process of converting a List to an int[] array may seem complicated, but starting with Java 8, it can be expressed more simply using lambda expressions and stream APIs.
