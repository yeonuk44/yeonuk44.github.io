---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Transparent_Proxy
title: About transparent proxy
# title: About transparent proxy
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Network
# multiple tag entries are possible
tags: [network]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-20 09:00:00 +0900
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

## "Swift 문법에 대하여 5"에 대하여

이번에 iOS에 대해 공부할 기회가 생겨 문법부터 공부하고 있었는데 이번에 이에 대해 정리하는 글을 남기고자 합니다.

이번 글에선 Set 타입에서의 다양한 함수 중 자주 사용되는 것을 소개하도록 하겠습니다.

우선 Set 타입은 무엇일까요?

{:data-align="center"}

<!-- outline-end -->

### Set 타입이란?

동일한 타입의 고유한 값들을 저장하는 컬렉션입니다.

순서가 보장되지 않으며, 각 요소는 한 번만 나타납니다.

#### 생성과 초기화

Set을 생성하고 초기화하는 방법입니다.

##### 예시

```swift
var color: Set<String> = ["Red", "Green", "Blue"]
```

#### insert

set에 요소를 추가합니다. 중복되는 값의 경우 추가되지 않습니다.

##### 예시

```swift
colors.insert("Yellow") // colors: ["Red", "Green", "Blue", "Yellow"]
```

#### remove

특정 요소를 제거합니다.

##### 예시

```swift
colors.remove("Green") // colors: ["Red", "Blue", "Yellow"]
```

#### contains

set에 특정 요소가 포함되어 있는지 확인합니다.

##### 예시

```swift
if colors.contains("Blue") {
    print("Contains Blue!")
}
// 출력: Contains Blue!
```

#### count

set의 요소 개수를 반환합니다.

##### 예시

```swift
let count = colors.count // count: 3
```

#### isEmpty

set이 비어있는지 확인합니다.

##### 예시

```swift
if colors.isEmpty {
    print("The set is empty")
} else {
    print("The set is not empty")
}
// 출력: The set is not empty
```

#### union

두개의 set을 합칩니다.

##### 예시

```swift
let moreColors: Set = ["Purple", "Yellow"]
let allColors = colors.union(moreColors) // allColors: ["Red", "Blue", "Yellow", "Purple"]
```

#### intersection

두 개의 set에 공통으로 포함된 요소를 찾습니다.

##### 예시

```swift
let commonColors = colors.intersection(moreColors) // commonColors: ["Yellow"]
```

#### subtracting

한 set에서 다른 set 요소를 제거합니다.

##### 예시

```swift
let exclusiveColors = colors.subtracting(moreColors) // exclusiveColors: ["Red", "Blue"]
```

#### symmetricDifference

두 개의 set에서 서로에게만 있는 요소를 찾습니다.

##### 예시

```swift
let differentColors = colors.symmetricDifference(moreColors) // differentColors: ["Red", "Blue", "Purple"]
```

### set은 어떤 상황에서 쓰는 것이 바람직한가?

고유한 요소들의 컬렉션을 관리할 때 유용하며, 수학적 집합 연산과 유사한 작업을 하기에 좋습니다.
