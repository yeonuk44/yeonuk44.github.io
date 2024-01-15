---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Swift_Syntax_1
title: Swift 문법에 대하여 1 (선언)
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

## "Swift 문법에 대하여 1 (선언)"에 대하여

이번에 iOS에 대해 공부할 기회가 생겨 문법부터 공부하고 있었는데 이번에 이에 대해 정리하는 글을 남기고자 합니다.

모든 언어가 그렇듯 선언에는 다양한 종류가 있습니다.

정리와 예시를 통해 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 변수 선언(var)

값을 저장하는 데 사용되며, 재할당이 가능합니다.

```swift
var name = "John"
```

### 상수 선언(let)

값을 저장하는 데 사용되며, 재할당이 불가합니다.

```swift
let pi :3.14159265
```

### 함수 선언(func)

코드의 동작을 정의하는 데 사용됩니다.

```swift
func add(a: Int, b: Int) -> Int {
    return a + b
}
```

### 클래스 선언(class)

객체 지향 프로그래밍의 클래스를 정의합니다.

```swift
class Dog {
    var name: String
    init(name: String) {
        self.name = name
    }
}
```

### 구조체 선언(struct)

값 타입을 정의하는 데 사용됩니다.

```swift
struct Point {
    var x: Double
    var y: Double
}
```

### 열거형 선언(enum)

관련된 값들의 그룹을 정의합니다.

```swift
enum Direction {
    case north
    case south
    case east
    case west
}
```

### 프로토콜 선언(protocol)

특정 요구 사항을 정의하는 데 사용됩니다.

```swift
protocol CanFly {
    func fly()
}
```

### 확장 선언(extension)

기존 타입에 새로운 기능을 추가합니다.

```swift
extension Int {
    var squared: Int {
        return self * self
    }
}
```

### 타입 별명 선언(typealias)

기존 타입에 대한 새로운 이름을 제공합니다.

```swift
typealias Length = Double
```
