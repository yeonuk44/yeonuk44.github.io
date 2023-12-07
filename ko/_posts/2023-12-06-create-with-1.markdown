---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Create_With_l
title: l로 만들기(with.Java)
# title: Create with l (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-12-06 09:00:00 +0900
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

## "l로 만들기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

알파벳 소문자로 이루어진 문자열 myString이 주어집니다.

알파벳 순서에서 "l"보다 앞서는 모든 문자를 "l"로 바꾼 문자열을 return 하는 solution 함수를 완성해 주세요.

#### 입출력 예시

| myString     | result       |
| ------------ | ------------ |
| "abcdevwxyz" | "lllllvwxyz" |
| "jjnnllkkmm" | "llnnllllmm" |

### 문제에 대한 나의 풀이

```java
class Solution {
    public static String solution(String myString) {
        char[] charArray = myString.toCharArray();
        for (int i = 0; i < charArray.length; i++) {
            if (charArray[i] < 'l') {
                charArray[i] = 'l';
            }
        }
        return new String(charArray);
    }
}
```

#### 풀이 설명

char[] charArray = myString.toCharArray();: 입력 문자열 myString을 문자 배열 charArray로 변환합니다. 이렇게 하면 문자열을 문자 단위로 접근할 수 있습니다.

for (int i = 0; i < charArray.length; i++) : 문자 배열 charArray를 반복하면서 각 문자에 대한 작업을 수행합니다.

if (charArray[i] < 'l') : 만약 현재 문자가 'l'보다 사전적 순서로 앞에 있는 문자라면:

해당 문자를 'l'로 대체합니다.

return new String(charArray);: 변경된 문자 배열 charArray를 다시 문자열로 변환하고 반환합니다.
