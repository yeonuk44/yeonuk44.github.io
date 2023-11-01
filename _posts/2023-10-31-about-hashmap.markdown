---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Hashmap
title: About HashMap(with.Java)
# title: Comparing Arrays (with.Java)
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
date: 2023-10-31 09:00:00 +0900
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

### This article introduces HashMap.

I'm preparing for a coding test, and I'm writing this down to introduce a useful tool in Java.

{:data-align="center"}

<!-- outline-end -->

#### What is a HashMap?

A HashMap is a data structure that stores key-value pairs, and retrieves and manipulates values based on keys. In Java, it is included in the java.util package.

#### Key features of a hashmap

- Stores key-value pairs: Hashmaps store data by associating keys with values. Keys are unique and never duplicated.
- Fast search speed: Hashmaps retrieve values based on keys, so you can find data quickly.
- No order: Hashmaps don't guarantee the order of your data, so it won't be retrieved in the order you stored it.
- No key duplication: The same key cannot be stored twice in a single hashmap. If a duplicate key is used, existing values will be replaced.
- Synchronization support: For safe use in multi-threaded environments, you can use Collections.synchronizedMap() to create a synchronized hashmap.

#### for a summary of frequently used methods in hashmaps

- put(key, value): Maps the specified key and value and adds them to the hashmap. If the same key already exists, the existing value will be replaced.
- get(key): Returns the value corresponding to the given key. Returns null if the key does not exist.
- containsKey(key): Checks whether the given key exists within the hashmap. Returns true if it exists, false otherwise.
- containsValue(value): Checks whether the specified value exists within the hashmap. Returns true if it exists, false otherwise.
- remove(key): Removes the value associated with the specified key from the hashmap.
- size(): Returns the number of key-value pairs stored in the hashmap.
- isEmpty(): Checks whether the hashmap is empty. Returns true if it is empty, false otherwise.
- clear(): Removes all key-value pairs within the hashmap, leaving it empty.
- keySet(): Returns a Set collection containing all the keys in the hashmap. This allows you to access all the keys.
- values(): Returns a Collection containing all the values in the hashmap. This allows you to enumerate all the values.
- entrySet(): Returns a Set collection containing the key-value pairs in the hashmap. This allows you to access all the key-value pairs.

#### Summary

In other words, hashmaps are one of the many Java Collection Framework classes that are particularly useful in situations where you need to store and retrieve data effectively.
