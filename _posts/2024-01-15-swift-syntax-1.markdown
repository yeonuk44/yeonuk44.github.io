---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Swift_Syntax_1
title: About Swift Syntax 1 (Declarations)
# title: About Swift Syntax 1 (Declarations)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Swift
# multiple tag entries are possible
tags: [swift, ios]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-15 09:00:00 +0900
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

## About "Swift syntax 1 (declarations)"

I recently had the opportunity to learn iOS and I've been working on the grammar, so I thought I'd write a post to summarize it.

As with any language, there are many different types of declarations.

Let's take a look at them with some examples

{:data-align="center"}

<!-- outline-end -->

### Variable declarations (var)

Used to store values, and can be reassigned.

```swift
var name = "John"
```

### Declaring a constant (let)

Used to store a value, which cannot be reassigned.

```swift
let pi :3.14159265
```

### Function declarations (func)

Used to define the behavior of code.

```swift
func add(a: Int, b: Int) -> Int {
    return a + b
}
```

### Class declaration (class)

Defines a class in object-oriented programming.

```swift
class Dog {
    var name: String
    init(name: String) {
        self.name = name
    }
}
```

### Struct declaration (struct)

Used to define a value type.

```swift
struct Point {
    var x: Double
    var y: Double
}
```

### Declaring an enumeration (enum)

Defines a group of related values.

```swift
enum Direction {
    case north
    case south
    case east
    case west
}
```

### Protocol declarations (protocol)

Used to define specific requirements.

```swift
protocol CanFly {
    func fly()
}
```

### Declaring an extension (extension)

Adds new functionality to an existing type.

```swift
extension Int {
    var squared: Int {
        return self * self
    }
}
```

### Declaring type aliases (typealias)

Provide new names for existing types.

```swift
typealias Length = Double
```
