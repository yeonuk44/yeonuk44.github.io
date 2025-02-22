---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Type_Of_Algorithm_With_Higher_Frequency_Compared_To_Enterprise_Coding_Tests
title: Type of algorithm with higher frequency compared to enterprise coding tests
# title: Type of algorithm with higher frequency compared to enterprise coding tests
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2025-02-22 09:00:00 +0900
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

## This article examines the types of algorithms with higher frequency compared to corporate coding tests.

Greetings after a long time. I've been put off writing due to personal reasons, but I'm thinking of getting myself together and rewriting it!

To prepare for the coding test again, today we looked at the types of algorithms with high frequency that are frequently asked.

{:data-align="center"}

<!-- outline-end -->

1. an optimization algorithm
   - Depending on the approach of the problem, there are types that need to be solved by the method of iterative statement recursive backtracking.
2. Prefix sum algorithm
   - There are ways to use number theory, and there are types that need to be solved by DP (top-down, bottom-up), memoization, etc. The problem of bottom-up DP type exists as a way to conceive the 'ignition equation'.
3. Full search
   - The most common type of cote, the type of solution by iterative statement recursive backtracking depending on the approach of the problem, exists.
4. 2D DP
   - Two-dimensional dynamic programming defines a problem in the form of a two-dimensional array and solves the entire problem by solving small problems, which is also used in problems such as string comparison and LIS/LCS. It stores the optimal solution of the partial problem using the array dp[i][j], and calculates the value of the current cell using the values of the previous cells.
5. LIS, LCS
   - LIS is a method of finding a partial sequence that satisfies the condition that each element is larger than the previous element among the partial sequences made by selecting some elements in the n-individual array with the longest increasing partial sequence.
   - LCS refers to a partial sequence/string that has a common element among two or more sequences or strings and has the longest length.
6. Two pointers
   - Two pointers are used to navigate an array or list, which solves the problem by moving the pointer to suit the conditions by clumsily moving the starting and ending points. It is usually used to find a specific sum in an array, or to find a sum in a continuous partial array.
7. Search for this person
   - An algorithm that looks for specific values in an array, halves the search range by comparing the intermediate elements of the array to the values you want to find. It is performed iteratively or recursively, and the time complexity is O(log n). It is mainly used to search for numbers, to find maximum/minimum values that satisfy conditions, and so on.
8. DFS / BFS
   - With graph navigation algorithms, DFS searches one path to the end and then returns to explore another, using a recursive or stack. BFS searches from the node close to the starting node, and uses a queue. DFS is mainly used for path navigation, maze search, and BFS is useful for shortest distance, and level-by-level navigation.
9. Dykstra
   - An algorithm that finds the shortest path from one vertex to all other vertices in a weighted graph. Use the priority queue to select the shortest path among the non-visited vertices, and to update the path of the adjacent vertices. It is mainly used for network path optimization, mapping applications, and so on.
10. Tree
    - It is used to efficiently explore and process data with hierarchical structures. Examples include binary trees, binary search trees, AVL trees, triples, etc. Mainly the types such as traversal (potential, median, posterior), insertion, deletion, search, etc.
