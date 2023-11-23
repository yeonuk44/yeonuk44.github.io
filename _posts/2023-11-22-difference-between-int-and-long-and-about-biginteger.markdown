---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Difference_Between_Int_And_Long_and_About_BigInteger
title: Difference between int and long and about BigInteger (with.Java)
# title: Difference between int and long and about BigInteger (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-11-22 09:00:00 +0900
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

## "Difference between int and long and about BigInteger" problem.

I was able to learn quite a bit more about the data types that I had come across while solving the questions in the coding test.

I'd like to share it with you in this post.

{:data-align="center"}

<!-- outline-end -->

### What do the int and long datatypes have in common?

Long and int are data types used to store integer values in Java.

#### Differences between int and long datatypes

1. range (Range):

   - INT: Represents a 32-bit integer. It is a signed integer and has a range of approximately -2,147,483,648 to 2,147,483,647.
   - Long: Represents a 64-bit integer. It is a signed integer and ranges from approximately -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807. This range is much larger than the range for int.

2. Memory Usage:

   - INT uses 4 bytes (32 bits) of memory.
   - A long uses 8 bytes (64 bits) of memory. Therefore, a long variable takes up twice as much memory.

3. Use Cases:

   - Int is sufficiently used in most situations. For example, they are used for array indices, iterated variables, and calculation results.
   - LONGs are used when you're dealing with very large integer values or need to perform calculations with high precision. They are also used to represent time or to deal with identifiers in large databases.

#### Summary

Int is used for common integer operations and is sufficient in most situations. However, if you need to deal with very large integer values or need to perform precise calculations, you can use long.

But what if we want to deal with integer values larger than 64 bits that are not handled by the long data type? This is where the BigInteger class comes in.

### What do long and BigInteger have in common?

Both long and BigInteger are data types that deal with integers.

### Differences between long and BigInteger

1. size limitations:

   - LONG: LONG is a 64-bit signed integer data type, which has a sufficient range for most situations. The minimum value is -9,223,372,036,854,775,808 and the maximum is 9,223,372,036,854,775,807. It can only handle integers within this range.
   - BigInteger: BigInteger represents an arbitrary precision integer with no precision limit. This means that it can handle integers of any size, there is no limit. Therefore, it is used when very large integers or precision is required.

2. exact:

   - LONG: LONG has a limited precision, which can cause accuracy issues when it can't accurately represent very large integers or very small decimals.
   - BigInteger: BigInteger has unbounded precision, so it can accurately perform very large integers or precise operations.

3. Usage

   - long: long is the default data type, and you can perform common integer operations using the default operators.
   - BigInteger: BigInteger is an object, so operations are performed through method calls. You create a BigInteger object and perform operations on it using methods such as add, subtract, multiply, and divide.

#### Summary

Long provides sufficient precision in most cases, and BigInteger is used when you need a very large or exact integer. During development, you should choose the appropriate type based on your needs.
