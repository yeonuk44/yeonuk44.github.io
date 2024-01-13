---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Multiple_Functions_For_String_Control
title: About multiple functions for string control
# title: About multiple functions for string control
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
date: 2024-01-13 09:00:00 +0900
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

## About "multiple functions for string control"

While testing my code, I realized that there are multiple functions for string control.

I would like to share them with you.

{:data-align="center"}

<!-- outline-end -->

### How to convert a string to upper and lower case

toUpperCase(): convert to upper case for English strings
toLowerCase(): Convert to lowercase for an English string

### How to determine if a string satisfies a condition based on a regular expression

Use regexObj.test(str).

Determines if the given string satisfies the regular expression, and returns true or false.

```javascript
const str = "table football";

const regex = new RegExp("foo*");
// Expected output: true
```

### How to utilize backslashes in strings

\To output the ": " outputs a pair of quotes
\": ' Print single quotes
Print the \\: Prints a \ character
\r: Move the cursor to the beginning of the line
\f: Move the cursor to the next page
\b: move the cursor one space
\t: Move the cursor by a tab
\n: Move the cursor to the next line.

#### Example

```javascript
var a = "My home is "Seoul"." : no output
var a = "My home is \"Seoul"\." : printable
```
