---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Multiple_Functions_For_Array_Control
title: About introducing multiple functions for array control
# title: About introducing multiple functions for array control
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Javascript
# multiple tag entries are possible
tags: [javascript]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-14 09:00:00 +0900
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

## About "multiple functions for array control"

While testing my code, I realized that there are multiple functions for controlling arrays.

I would like to share them with you.

{:data-align="center"}

<!-- outline-end -->

### How to insert a value into an array

Array.prototype.push() adds one or more elements to the end of the array, and returns the new length of the array.
Example

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

### How to concatenate all the elements of an array into a single string?

Use Array.join().
Example.

```javascript
const elements = ["Fire", "Air", "Water"];

console.log(elements.join());
// Expected output: "Fire,Air,Water"

console.log(elements.join(""));
// Expected output: "FireAirWater"

console.log(elements.join("-"));
// Expected output: "Fire-Air-Water"
```

### How to iterate through all elements of an array in ascending order

Use forEach(). forEach() executes the given callback once for each element in the array, in ascending order. It does not run against index properties that have been deleted or uninitialized (for example, sparse arrays).
callback is called with three arguments: the element value, the element index, and the array being traversed.

Example of skipping iteration over uninitialized values

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

Example of replacing a for() loop with forEach()

```javascript
const items = ["item1", "item2", "item3"];
const copy = [];

// before
for (let i = 0; i < items.length; i++) {
  copy.push(items[i]);
}

// after
items.forEach(function (item) {
  copy.push(item);
});
```

Example of controlling a specific index element of an array

````javascript
const months = ["Jan", "March", "April", "June"];

// Inserts at index 1
console.log(months.splice(1, 0, "Feb"));
// Expected output: Array ["Jan", "Feb", "March", "April", "June"]

months.splice(4, 1, "May");
// Replaces 1 element at index 4
// Expected output: Array ["Jan", "Feb", "March", "April", "May"]

console.log(months.splice(2, 2, "May"));
// Expected output: Array ["Jan", "Feb", "May"]
// Console output: Array ["March", "April"]
// Excluded elements are output as an array

console.log(months);
// Expected output: Array ["Jan", "Feb", "May", "May"]
``` Translated with www.DeepL.com/Translator (free version)
````
