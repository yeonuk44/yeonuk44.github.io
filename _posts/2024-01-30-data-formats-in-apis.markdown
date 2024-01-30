---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Data_Formats_In_APIs
title: About understanding data formats in APIs
# title: About understanding data formats in APIs
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
date: 2024-01-30 09:00:00 +0900
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

## 개요

JavaScript에서 모듈 시스템은 코드를 구성하고 재사용하는 데 중요한 역할을 합니다.

CommonJS와 ES Module은 이러한 모듈 시스템의 두 가지 주요 구현 방식입니다. 각각의 특징과 차이점에 대해 알아봅시다.

<!-- outline-end -->

### CommonJS (require)

#### 특징

- 동기적 로딩: require 함수를 통해 모듈을 동기적으로 로딩합니다.
- 런타임 로딩: 모듈은 런타임에서 동적으로 로딩됩니다.
- 객체 기반: 모듈은 객체로 표현되며, 해당 객체의 프로퍼티나 메서드를 사용하여 - 내보낸 모듈의 요소에 액세스합니다.
- 서버 사이드(Node.js): 주로 서버 사이드에서 사용되며, Node.js 환경에서 기본적으로 지원됩니다.

#### 사용예시

```javascript
const fs = require("fs");
const utils = require("./utils");

// 모듈 사용
console.log(utils.add(2, 3));
```

### ES Module (import/export)

#### 특징

- 비동기적 로딩: 모듈은 비동기적으로 로딩됩니다. import 문은 비동기적으로 동작하며, 프라미스를 반환합니다.
- 정적 로딩: 모듈은 정적으로 로딩되며, 코드가 실행되기 전에 로딩됩니다.
- 객체 기반: export와 import 구문을 사용하여 모듈의 특정 부분을 내보내거나 가져올 수 있습니다.
- 브라우저 및 서버 사이드: 최신 브라우저에서도 지원되며, Node.js에서도 ES Module을 사용할 수 있습니다.

#### 사용예시

```javascript
// 모듈 내보내기
// utils.js
export function add(a, b) {
  return a + b;
}

// 모듈 가져오기
// main.js
import { add } from "./utils";

// 모듈 사용
console.log(add(2, 3));
```

## 결론

CommonJS는 주로 서버 사이드(Node.js)에서 사용되는 반면, ES Module은 서버 및 클라이언트 측에서 모두 사용 가능합니다.

CommonJS는 동기적 로딩이고 런타임 로딩을 지원하는 반면, ES Module은 비동기적 로딩이며 정적 로딩을 수행합니다.

CommonJS는 module.exports 및 require를 사용하여 모듈을 정의하고 가져오는 반면, ES Module은 export 및 import를 사용합니다.

모듈 시스템의 선택은 환경과 사용 사례에 따라 다르며, 프로젝트의 요구 사항에 따라 적절한 방법을 선택해야 합니다.
