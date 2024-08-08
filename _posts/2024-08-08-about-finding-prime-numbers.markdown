---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_Prime_Numbers
title: Finding prime numbers (with.Java)
# title: Finding prime numbers (with.Java)
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
date: 2024-08-08 09:00:00 +0900
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

## This is an article about the problem of finding prime numbers (with.Java).

I would like to solve the coding test problem and reflect on the problem I solved.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Pieces of paper with single digits are scattered.

I'm trying to figure out how many primes I can make by attaching scattered pieces of paper.

Given the string numbers written on each piece of paper, complete the solution function so that you can return how many prime numbers can be made from the piece of paper.

#### Restrictions

- Numbers are strings that are greater than or equal to 1 and less than or equal to 7.
- Numbers consist of only numbers from 0 to 9.
- "013" means that there are scattered pieces of paper with the numbers 0, 1, and 3.

#### Input/Output Examples

| numbers | return |
| ------- | ------ |
| "17"    | 3      |
| "011"   | 2      |

### my solution to the problem

```java
import java.util.Set;
import java.util.HashSet;

class Solution {
    private Set<Integer> numSet = new HashSet();
    public int solution(String numbers) {
        char[] numArr = numbers.toCharArray();
        for(int i = 1; i <= numArr.length; i++)
            makeCase(numArr, 0, i, new int[numArr.length], new boolean[numArr.length]);
        return numSet.size();
    }

    private void makeCase(char[] numArr, int cnt, int size, int[] idxArr, boolean[] visit){
        if(cnt == size){
            String numStr = "";
            for(int i = 0; i < size; i++) numStr += numArr[idxArr[i]];
            int num = Integer.parseInt(numStr);
            if(isPrime(num)) numSet.add(num);
            return;
        }

        for(int i = 0; i < numArr.length; i++){
            if(!visit[i]){
                visit[i] = true; idxArr[cnt] = i;
                makeCase(numArr, cnt+1, size, idxArr, visit);
                visit[i] = false;
            }
        }
    }

    private boolean isPrime(int n){
        if(n < 2) return false;
        for(int i = 2; i <= Math.sqrt(n); i++)
            if(n % i == 0) return false;
        return true;
    }
}
```

### Solution Description

- The solution method takes string numbers as input.
- Split each number by converting the numbers into a character array.
- Invoke the makeCase method to generate all possible combinations with each number.
- The makeCase method is recursively called and uses backtracking to generate all possible combinations.
- Within the makeCase method, use an array idxArr that stores the currently selected index and an array visit that indicates if that index has been visited.
- After each combination is completed, determine if the number is prime and add it to the numSet.
- The isPrime method determines whether a given number is a prime number.
- After all combination creation has been completed, return the size of the numSet to obtain a prime number.

### Conclusion

This code solves the problem of using backtracking to generate all possible combinations with a given number, and returning the number of prime numbers among them.
