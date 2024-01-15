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

## "배열 제어에 대한 여러 함수"에 대하여

코딩 테스트를 진행하며, 배열 제어에 대한 여러 함수가 있다는 것을 알게 되었습니다.

이에 공유하고자 합니다.

{:data-align="center"}

<!-- outline-end -->

### 배열에 값을 삽입하는 방법

Array.prototype.push()는 배열의 끝에 하나 이상의 요소를 추가하고, 배열의 새로운 길이를 반환합니다.

예시

```javascript
const animals = ["pigs", "goats", "sheep"];

const count = animals.push("cows");
console.log(count);
// Expected output: 4
console.log(animals);
// Expected output: Array ["pigs", "goats", "sheep", "cows"]

animals.push("chickens", "cats", "dogs");
console.log(animals);
// Expected output: Array ["pigs", "goats", "sheep", "cows", "chickens", "cats", "dogs"]
```

### 배열의 모든 요소를 연결해 하나의 문자열로 만드는 방법

Array.join()을 사용합니다.
예시

```javascript
const elements = ["Fire", "Air", "Water"];

console.log(elements.join());
// Expected output: "Fire,Air,Water"

console.log(elements.join(""));
// Expected output: "FireAirWater"

console.log(elements.join("-"));
// Expected output: "Fire-Air-Water"
```

### 배열의 모든 요소를 오름차순으로 반복하는 방법

forEach()를 사용합니다. forEach()는 주어진 callback을 배열에 있는 각 요소에 대해 오름차순으로 한 번씩 실행합니다.

삭제했거나 초기화하지 않은 인덱스 속성에 대해서는 실행하지 않습니다. (예: 희소 배열)

callback은 요소 값, 요소 인덱스, 순회 중인 배열 총 3개의 인수와 함께 호출됩니다.

초기화하지 않은 값의 반복 생략 예시

```javascript
const arraySparse = [1, 3, , 7];
let numCallbackRuns = 0;

arraySparse.forEach(function (element) {
  console.log(element);
  numCallbackRuns++;
});

console.log("numCallbackRuns: ", numCallbackRuns);

// 1
// 3
// 7
// numCallbackRuns: 3
// comment: as you can see the missing value between 3 and 7 didn't invoke callback function.
```

for() 반복문 대신 forEach()로 바꾸는 예시

```javascript
const items = ["item1", "item2", "item3"];
const copy = [];

// 이전
for (let i = 0; i < items.length; i++) {
  copy.push(items[i]);
}

// 이후
items.forEach(function (item) {
  copy.push(item);
});
```

배열의 특정 인덱스 요소 제어하는 예시

```javascript
const months = ["Jan", "March", "April", "June"];

// Inserts at index 1
console.log(months.splice(1, 0, "Feb"));
// Expected output: Array ["Jan", "Feb", "March", "April", "June"]

months.splice(4, 1, "May");
// Replaces 1 element at index 4
// Expected output: Array ["Jan", "Feb", "March", "April", "May"]

console.log(months.splice(2, 2, "May"));
// Expected output: Array ["Jan", "Feb", "May"]
// Console output:  Array ["March", "April"]
// 제외된 요소가 배열로 출력됩니다.

console.log(months);
// Expected output: Array ["Jan", "Feb", "May", "May"]
```
