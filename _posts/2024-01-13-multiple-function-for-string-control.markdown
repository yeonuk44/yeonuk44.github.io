---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Multiple_Functions_For_String_Control
title: About multiple functions for string control
# title: About multiple functions for string control
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
date: 2024-01-13 09:00:00 +0900
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

## "문자열을 배열로 변환하는 방법"에 대하여

코딩 테스트를 진행하며, 문자열을 배열로 변환하는 방법에는 많은 방법이 있다는 것을 알게 되었습니다.

이에 공유하고자 합니다.

{:data-align="center"}

<!-- outline-end -->

### for문을 활용해 배열로 만드는 방법

```javascript
const str = "Hello";
const arr = [];

for (let i = 0; i < str.length; i++) {
  arr.push(str[i]);
}

console.log(arr); // ["H", "e", "l", "l", "o"]
```

위 코드에서 for 루프를 사용하여 i 변수를 0부터 시작하여 str.length까지 1씩 증가시키면서, str의 각 문자를 arr 배열에 push 메서드를 사용하여 추가합니다.

이렇게 하면 문자열의 각 문자가 배열의 각 요소로 들어가게 됩니다.

위의 예제를 실행하면 "Hello" 문자열이 배열로 변환되어 arr 변수에 저장되고, console.log(arr)을 통해 배열이 출력됩니다.

출력 결과는 ["H", "e", "l", "l", "o"]가 됩니다.

### split문을 활용해 배열로 만드는 방법

```javascript
const str = "Hello";
const arr = str.split(""); // 빈 문자열을 구분자로 사용하여 문자열을 배열로 변환
console.log(arr); // ["H", "e", "l", "l", "o"]
```

for문과 비슷한 현상을 보이기에 설명은 생략하겠습니다.

### 배열 리터럴을 활용해 배열로 만드는 방법

```javascript
const str = "Hello";
const arr = [...str]; // 배열 리터럴을 사용하여 문자열을 배열로 변환
console.log(arr); // ["H", "e", "l", "l", "o"]
```
