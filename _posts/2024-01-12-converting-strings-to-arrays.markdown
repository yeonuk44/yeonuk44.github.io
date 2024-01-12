---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_converting_strings_to_arrays
title: About converting strings to arrays
# title: About converting strings to arrays
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Javascript
# multiple tag entries are possible
tags: [javascript]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-12 09:00:00 +0900
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

## About "How to convert a string to an array"

While testing our code, we realized that there are many ways to convert strings to arrays.

We'd like to share them with you.

{:data-align="center"}

<!-- outline-end -->

### How to make an array using a for statement

```javascript
const str = "Hello";
const arr = [];

for (let i = 0; i < str.length; i++) {
  arr.push(str[i]);
}

console.log(arr); // ["H", "e", "l", "l", "o"]
```

In the above code, the for loop is used to increment the i variable by 1, starting at 0, up to str.length, while adding each character of str to the array arr using the push method.

This ensures that each character of the string is pushed into each element of the array.

When you run the above example, the string "Hello" is converted to an array, stored in the arr variable, and the array is output via console.log(arr).

The output will be ["H", "e", "l", "l", "o"].

### How to create an array using the split statement

```javascript
const str = "Hello";
const arr = str.split(""); // Convert a string to an array using an empty string as a separator
console.log(arr); // ["H", "e", "l", "l", "o"]
```

This is similar to the for statement, so I'll skip explaining it.

### How to take an array literal and make it an array

```javascript
const str = "Hello";
const arr = [...str]; // Convert a string to an array using array literals
console.log(arr); // ["H", "e", "l", "l", "o"]
```
