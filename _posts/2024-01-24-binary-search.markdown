---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Binary_Search
title: About Binary Search
# title: About Binary Search
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
date: 2024-01-24 09:00:00 +0900
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

## About "Binary Search"

The binary search algorithm is one of the most important and efficient search algorithms in computer science and algorithm theory.

It is used to find specific values within a data set, or to efficiently find elements that satisfy a condition.

In this article, we'll learn about the concept of binary search, how it works, its implementation, and its use in real-world situations.

{:data-align="center"}

<!-- outline-end -->

### What is Binary Search?

Binary search is an algorithm for finding a desired value within a sorted data set.

It works by dividing the data in half, reducing the search range by half, and then finding the desired value.

This iterative process allows you to find the desired value very quickly.

### How binary traversal works

- Select the middle element.
- Compare the selected element to the value you're looking for.
- If the selected element is the same as the value you are looking for, the search ends.
- If the selected element is greater than the value you're looking for, search again, leaving only the right half.
- If the selected element is less than the value you are looking for, search again with only the left half.

Repeat the process until the desired value is found.

### Implementing binary traversal

Binary traversal can be implemented via recursion or looping.

Below is a simple implementation of binary traversal using a loop.

```java
int binarySearch(int arr[], int target) {
    int left = 0, right = arr.length - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;

        if (arr[mid] == target)
            return mid;

        if (arr[mid] < target)
            left = mid + 1;
        else
            right = mid - 1;
    }

    return -1; // if not found
}

```

### Utilizing Binary Navigation

Binary traversal is used to check for the existence of a specific value within an array, or to quickly find a desired value.

For example, it is very useful for finding an item in a sorted list, or checking the existence of a value within a certain range.

Binary traversal is actively used in database query optimization, game programming, search engines, and sorting algorithms.

### Conclusion

Binary traversal is an efficient algorithm for quickly finding a desired value in a sorted data set.

By understanding and utilizing this algorithm, you can better solve many problems related to data retrieval.
