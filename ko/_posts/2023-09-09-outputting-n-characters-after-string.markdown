---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Outputting_n_Characters_After_String
title: 문자열 뒤의 n글자 출력에 대하여(with.Java)
# title: For outputting n characters after a string (with.Java)

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
date: 2023-09-09 09:00:00 +0900
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

### 문자열 뒤의 n글자 출력에 대하여(with.Java) 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 my_string과 정수 n이 매개변수로 주어질 때, my_string의 뒤의 n글자로 이루어진 문자열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "ProgrammerS123"

n: 11

result: "grammerS123"

my_string에서 뒤의 11글자는 "grammerS123"이므로 이 문자열을 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String my_string, int n) {
        String answer = "";
        answer = my_string.substring(my_string.length() - n);
        return answer;
    }
}
```

##### 풀이 설명

my_string은 문자열로 제공되기 때문에 substring으로 뒷 요소를 잘라 출력하면 된다고 생각하여 answer 변수에 my_string.substring(my_string.length() - n);으로 전체 길이-n으로 뒷부분에서 index만큼 출력하였습니다.

이게 가능한 것은 substring()은 자른 것에 대해 값을 반환해주기 때문입니다.

전체 길이에서 n을 뺀 이유는 그냥 substring(n)을 할 경우 substring 특성상 n이 11일 때 my_string의 11번째 index부터 문자열을 자릅니다. 그러면 123이 출력될 것입니다.

그렇기 때문에 반대로 my_string의 전체 길이에서 n을 뺀 값을 substring에 삽입할 경우 그 값만큼만 문자열이 남고 뒷 문자열은 substring에 의해 잘려 반환됩니다.

이 케이스를 이용해 문자열 뒤의 n글자가 출력되도록 구현했습니다.
