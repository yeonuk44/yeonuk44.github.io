---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Syntax_Of_Python
title: About the basic syntax of Python
# title: About the basic syntax of Python
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Python
# multiple tag entries are possible
tags: [python]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-03-19 09:00:00 +0900
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

## This is an article about the basic syntax of Python.

Python is a programming language famous for its concise and easy-to-read syntax.

Let’s find out through an example together.

{:data-align="center"}

<!-- outline-end -->

### Variables and data types

There is no need to specify a separate type when declaring a variable in Python.

For example, you can declare a variable like this:

```python
name = "Alice"
age = 25
height = 165.5
```

In the above example, name is a string, age is an integer type, and height is a real number variable.

### Conditional statement (if statement)

Conditional statements in Python can be written using the if, elif, and else keywords.

For example, you can write a conditional statement like this:

```python
x = 10

if x > 0:
     print("It's a positive number.")
elif x < 0:
     print("It's a negative number.")
else:
     print("It's 0.")
```

In the above example, it determines whether variable x is positive, negative, or 0 and outputs the result.

### Loop statement (for statement)

Python's for statement is used to iterate through sequence data types.

For example, you can traverse the list and output elements as follows:

```python
fruits = ["apple", "banana", "strawberry"]

for fruit in fruits:
     print(fruit)
```

In the above example, the elements of the list called fruits are iterated one by one and output.

### function

When defining functions in Python, use the def keyword.

For example, you could define a greeting function like this:

```python
def say_hello(name):
     print("Hello, " + name + "!")

say_hello("Alice")
```

In the example above, a function called say_hello is defined and the function is called to output “Hello, Alice!”

## Conclusion

We briefly looked at the basic syntax and examples of Python.

Python has a concise and readable syntax and is used in a variety of programming fields.

Next time, we will meet you on more diverse topics. thank you
