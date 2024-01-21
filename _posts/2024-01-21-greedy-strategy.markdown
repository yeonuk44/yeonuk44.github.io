---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Greedy_Strategy
title: About the Greedy Strategy
# title: About the Greedy Strategy (Greedy Algorithm)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Algorithm
# multiple tag entries are possible
tags: [algorithm]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-21 09:00:00 +0900
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

## About the "Greedy Strategy" algorithm

In this article, we'll discuss what the Greedy Strategy is, how it works, and in what situations it can be useful.

{:data-align="center"}

<!-- outline-end -->

### Introduction

The Greedy Strategy, or Greedy Algorithm, is one of the techniques that plays an important role in algorithmic theory.

It is one of the ways to find an optimal solution by always behaving in a way that makes the best choice in the current situation.

For more information, see: #### What is Greedy Strategy?

A greedy strategy is an algorithm that makes the best choice at every moment.

It works by iterating over the best choice at the current point in time to get to the final result, where the choice is the most ideal choice at each step.

It is based on the belief that if this choice is optimal at each step, it will be optimal overall.

The key to the Greedy Strategy is to follow a simple rule.

It's about finding the optimal choice at each moment, and making sure that choice is optimal overall.

The Greedy algorithm works by breaking the problem into subproblems, finding the optimal solution for each subproblem, and then finding the optimal solution for the whole problem.

#### Examples of Greedy Strategies

- Change Problem: In the problem of giving change in the smallest number of coins, choosing the largest denomination coin first is an example of a Greedy algorithm.
- Prim algorithm: The Prim algorithm, which finds the minimum spanning tree, utilizes a Greedy approach to select the trunk line with the smallest weight.
- Kruskal algorithm: Another minimum spanning tree algorithm, the Kruskal algorithm sorts trunk lines in ascending order of weight and selects trunk lines that do not form a cycle.
- Dijkstra algorithm: In the shortest path problem, the Dijkstra algorithm uses a greedy approach to select the shortest path.

#### Limitations of the Greedy Strategy

While the Greedy Strategy is useful for many problems, it is not suitable for all problems.

The Greedy algorithm finds the optimal choice at each step, but that choice does not guarantee an overall optimal solution.

In some problems, the Greedy approach may not converge to the optimal solution.

You should understand these limitations and decide whether to use Greedy based on the nature of your problem.

#### Conclusion

The Greedy Strategy is a powerful tool that can solve a wide variety of problems in a simple and intuitive way.

However, it is not applicable to all problems, and the optimal solution should be chosen based on the characteristics of each problem.

The Greedy algorithm works by finding the optimal choice at each step, which makes it useful for decomposing problems and optimizing each subproblem.
