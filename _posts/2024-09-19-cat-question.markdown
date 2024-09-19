---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Cat_Question
title: Baekjun 10171, Cat (with.Java)
# title: Baekjun 10171, Cat (with.Java)
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
date: 2024-09-19 09:00:00 +0900
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

## This is an article about Baekjun (with.Java) No.10171.

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Print out the cat as in the example below.

#### Input

None.

#### Output

It prints out a cat.

### problem solving

```java
class Main {
	public static void main(String[] args) {

		System.out.println("\\    /\\");
		System.out.println(" )  ( ')");
		System.out.println("(  /  )");
		System.out.println(" \\(__)|");

	}
}

```

#### Solution Description

'\\' outputs \.
() outputs parentheses.
| outputs a pipe.`

This code uses an escape sequence to output special characters, and each System.out.println statement is printed one line at a time.

I knew that solving the problem was possible only when I knew about the escape sequence.

What is Escape Sequence
Escape sequences are used to represent characters with special meanings within strings. They are usually used to include control characters or special characters in strings. Escape sequences begin with a backslash (`\`) and perform various functions depending on the characters that follow.

Key Escape Sequences

`\\ : means the backslash (\) itself.
\' : means lower quotation marks (').
\" : means double quotation marks (").
\n : Change Line (move to new line)
\t : Tab characters (typically 4 or 8 spaces)
\r : carriage return (go to the beginning of the line)
\b : Backspace (delete old characters)
\f : Form Feed (Divide pages)
\uXXXX: Unicode character (XXXX is a 4-digit hexadecimal)`

### Conclusion

If the code contains double quotes ("") and reverse slashes ('\') when expressing characters with special meanings, you can put one reverse slash before the character with special meanings.

Thank you!
