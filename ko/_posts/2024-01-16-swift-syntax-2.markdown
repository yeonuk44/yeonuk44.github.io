---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Swift_Type_2
title: Swift 문법에 대하여 2 (타입)
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
date: 2024-01-16 09:00:00 +0900
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

## "Swift 문법에 대하여 2 (타입)"에 대하여

이번에 iOS에 대해 공부할 기회가 생겨 문법부터 공부하고 있었는데 이번에 이에 대해 정리하는 글을 남기고자 합니다.

Swift에는 다양한 타입이 있습니다.

이번 글에선 타입에 대해 소개하고자 합니다.

{:data-align="center"}

<!-- outline-end -->

1. Integers
   정수형을 나타내며, 부호가 있는 Int와 부호가 없는 UInt가 있습니다.
   예시

```swift
var positiveNumber: Int = 42
var unsignedNumber: UInt = 7
```

2. Floating-Poin Number
   실수를 표현하며, Float와 Double 타입이 있습니다.
   예시

```swift
var floatNumber: Float = 3.14
var doubleNumber: Double = 3.1415926535
```

3. String
   텍스트를 표현하는 문자열 타입입니다.
   예시

```swift
var string: String = "Hello, Swift!"
```

4. Booleans
   참 또는 거짓을 표현합니다.
   예시

```swift
var isTrue: Bool = true
var isFalse: Bool = false
```

5. Tuples
   여러 값들을 하나의 그룹으로 묶을 수 있는 타입입니다.
   예시

```swift
var person: (String, Int) = ("John", 35)
```

6. Optional
   값이 있을 수도 있고, 없을 수도 있는 상황을 표현하는 타입입니다.
   예시

```swift
var optionalString: String? = nil
optionalString = "Now it has a value"
```

7. Array
   같은 타입의 여러 값들을 순서대로 저장하는 컬렉션 타입입니다.
   예시

```swift
var fruits: [String] = ["Apple", "Banana", "Cherry"]
```

8. Dictionary
   Key - Value를 쌍으로 데이터를 저장하는 컬렉션 타입입니다.
   예시

```swift
var ages: [String: Int] = ["John": 28, "Sarah": 25]
```

9. Set
   중복 없이 같은 타입의 여러 값을 저장하는 컬렉션 타입입니다.
   예시

```swift
var uniqueNumbers: Set<Int> = [1, 2, 2, 3, 3, 3]
// uniqueNumbers is now {1, 2, 3}
```

10. Enumerations
    관련된 값들을 그룹화하여 작업하는 타입입니다.

```swift
enum CompassPoint {
    case north
    case south
    case east
    case west
}
var direction: CompassPoint = .north
```
