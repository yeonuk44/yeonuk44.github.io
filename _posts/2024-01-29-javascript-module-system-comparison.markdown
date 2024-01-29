---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_JavaScript_module_system_comparison
title: About JavaScript module system comparison
# title: About JavaScript module system comparison
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
date: 2024-01-29 09:00:00 +0900
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

## outline

In JavaScript, the module system plays an important role in organizing and reusing code.

CommonJS and ES Module are the two main implementations of these module systems. Let’s learn about the characteristics and differences of each.

<!-- outline-end -->

### CommonJS (require)

#### characteristic

- Synchronous loading: Loads modules synchronously through the require function.
- Runtime loading: Modules are loaded dynamically at runtime.
- Object-based: A module is represented as an object, and you use the properties or methods of that object to access elements of the exported module.
- Server side (Node.js): Mainly used on the server side and supported by default in the Node.js environment.

#### Example of use

```javascript
const fs = require("fs");
const utils = require("./utils");

// use module
console.log(utils.add(2, 3));
```

### ES Module (import/export)

#### characteristic

- Asynchronous loading: Modules are loaded asynchronously. The import statement operates asynchronously and returns a promise.
- Static loading: Modules are loaded statically, and are loaded before the code is executed.
- Object-based: You can export or import specific parts of a module using the export and import statements.
- Browser and server side: Supported by the latest browsers, ES Module can also be used in Node.js.

#### Example of use

```javascript
// export module
//utils.js
export function add(a, b) {
  return a + b;
}

// import module
//main.js
import { add } from "./utils";

// use module
console.log(add(2, 3));
```

## conclusion

CommonJS is mainly used on the server side (Node.js), while ES Module can be used on both the server and client sides.

CommonJS is synchronous loading and supports runtime loading, while ES Module is asynchronous loading and performs static loading.

CommonJS uses module.exports and require to define and import modules, while ES Module uses export and import.

The choice of modular system depends on the environment and use case, and the appropriate method should be selected according to the requirements of the project.
