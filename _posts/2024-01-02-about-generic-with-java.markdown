---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Generic
title: About Generic (with. Java)
# title: About Generic (with. Java)
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
date: 2024-01-02 09:00:00 +0900
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

## This is a post about the "About Generics" issue.

I was looking at other people's work and came across the <T> type.

I remember seeing it when I was an undergraduate learning static languages (Java, C, etc.).

It's been a while since I've seen one, so I thought I'd share.

{:data-align="center"}

<!-- outline-end -->

### Concept

Generics are one of the important features of the Java programming language.

It provides the ability to parameterize types when defining a class or method.

Generics allow you to not specify a type when you declare a class or method, but to specify a concrete type when you use it.

This makes your code more reusable and type-safe.

### Basic structure of generics

To use generics in Java, you use type parameters when defining classes, interfaces, and methods.

A type parameter is a type of data type that is replaced by a concrete type when it is actually used.

1. Using generics in a class

```java
public class Box<T> {
    private T data;

    public void setData(T data) {
        this.data = data;
    }

    public T getData() {
        return data;
    }
}
```

In the example above, the Box class uses generics to represent a box that holds data.

T is the type parameter, which indicates what type of data you will be dealing with when you actually use the class.

2. Using generics in methods

```java
public <T> T findFirst(List<T> list) {
    if (list != null && !list.isEmpty()) {
        return list.get(0);
    }
} return null;
```

In the above example, the findFirst method uses generics to return the first element of the list.

The <T> in the method declaration indicates that the method uses the generic type.

#### Advantages of generics

Type Safety: Using generics makes it easier for the compiler to catch type-related errors in your code. Type conversion errors that might occur at runtime can be caught at compile time.

Code reusability: Generics allow you to use one class or method for many different kinds of types. This makes your code more reusable.

Generalization of algorithms: Generics allow you to write algorithms more generally. You can write algorithms that can be used on many types without relying on a specific type.

#### Examples of generics

```java
public class Main {
    public static void main(String[] args) {
        // Example of generics using the Box class
        Box<String> stringBox = new Box<>();
        stringBox.setData("Hello, Generics!");
        String data = stringBox.getData();
        System.out.println(data);

        // Example utilizing generic methods
        List<Integer> integerList = List.of(1, 2, 3, 4, 5);
        Integer firstElement = findFirst(integerList);
        System.out.println("First element: " + firstElement);
    }

    } public static <T> T findFirst(List<T> list) {
        if (list != null && !list.isEmpty()) {
            return list.get(0);
        }
} return null;
```

In the above example, the Box class is used to create a box with string data, and the findFirst method is used to find the first element of a list of integers.

These examples should give you a good idea of how generics are used.

### Conclusion

Generics are a powerful feature in Java, making your code more reusable and type-safe.

By parameterizing types when defining classes, interfaces, and methods, we can be flexible in dealing with different types.

By utilizing generics, the compiler can proactively detect more errors and increase the generality and extensibility of your code.

By properly utilizing generics, Java programmers can write more concise and reliable code.
