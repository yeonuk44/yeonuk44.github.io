---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Vertical_Reading
title: 세로 읽는 방법에 대하여(with.Java)
# title: About Vertical Reading (with.Java)

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
date: 2023-09-14 09:00:00 +0900
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

### 세로 읽는 방법에 대하여(with.Java) 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 my_string과 두 정수 m, c가 주어집니다.

my_string을 한 줄에 m 글자씩 가로로 적었을 때 왼쪽부터 세로로 c번째 열에 적힌 글자들을 문자열로 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "ihrhbakrfpndopljhygc"

m: 4

c: 2

result: "happy"

my_string을 한 줄에 4 글자씩 쓰면 다음의 표와 같습니다.

| 1열 | 2열 | 3열 | 4열 |
| --- | --- | --- | --- |
| i   | h   | r   | h   |
| b   | a   | k   | r   |
| f   | p   | n   | d   |
| o   | p   | l   | j   |
| h   | y   | g   | c   |

2열에 적힌 글자를 세로로 읽으면 happy이므로 "happy"를 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String my_string, int m, int c) {
        char[] arr = my_string.toCharArray();
        char[] arr1 = new char[arr.length/m];
        int j = 0;
        for(int i = c-1; i < arr.length; i+=m){
            arr1[j++] = arr[i];
        }
        return new String(arr1);
    }
}
```

##### 풀이 설명

행렬을 정립하기 위해 우리는 먼저 문자열 타입을 Char 타입으로 바꿔 배열로 저장할 필요가 있습니다.

이에 char[] 타입의 arr에 my_string을 toCharArray()를 통해 저장합니다.

이후 return 값을 저장할 arr1도 동일한 타입으로 지정 후, 배열의 크기는 arr의 길이에서 몇 열까지인지 알 수 있으면 됩니다.

따라서 나눈 다음 반복문을 선언하여 문제에서 요구하는 방식으로 조건을 설정하고 행렬에서 특정한 idx의 요소를 저장하여 반환했습니다.
