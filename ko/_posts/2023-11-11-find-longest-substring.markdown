---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Find_Longest_SubString
title: 특정 문자열로 끝나는 가장 긴 부분 문자열 찾기(with.Java)
# title: Find the longest substring ending in a specific string (with.Java)
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
date: 2023-11-11 09:00:00 +0900
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

### "특정 문자열로 끝나는 가장 긴 부분 문자열 찾기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 myString과 pat가 주어집니다.

myString의 부분 문자열중 pat로 끝나는 가장 긴 부분 문자열을 찾아서 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

| myString   | pat  | result     |
| ---------- | ---- | ---------- |
| "AbCdEFG"  | "dE" | "AbCdE"    |
| "AAAAaaaa" | "a"  | "AAAAaaaa" |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String myString, String pat) {
        StringBuilder answer = new StringBuilder();
        StringBuilder answer1 = new StringBuilder();
        for(int i = 0; i < myString.length(); i++){
            answer.append(myString.charAt(i));
        }
        int count = answer.lastIndexOf(pat);
        answer1.append(answer.substring(0,count));
        for(int j = 0; j < pat.length(); j++){
            answer1.append(pat.charAt(j));
        }
        return answer1.toString();
    }
}
```

##### 풀이 설명

StringBuilder answer = new StringBuilder(); 및 StringBuilder answer1 = new StringBuilder();: 두 개의 StringBuilder 객체 answer와 answer1을 생성합니다. 이 객체들은 문자열을 효율적으로 조작할 수 있도록 도와줍니다.

for(int i = 0; i < myString.length(); i++): 입력 문자열 myString을 반복하면서 각 문자를 answer에 추가합니다. 이렇게 하면 answer에는 myString의 내용이 그대로 들어가게 됩니다.

int count = answer.lastIndexOf(pat);: answer 문자열에서 pat 문자열의 마지막 등장 위치를 찾아서 count에 저장합니다.

answer1.append(answer.substring(0, count)): answer 문자열에서 pat 문자열의 마지막 등장 위치까지의 부분 문자열을 answer1에 추가합니다. 이 부분은 pat 이전의 문자열입니다.

for(int j = 0; j < pat.length(); j++): pat 문자열의 각 문자를 answer1에 추가합니다.

return answer1.toString();: 최종적으로 조합된 answer1 문자열을 문자열로 변환하여 반환합니다.

이 코드는 입력 문자열 myString에서 마지막으로 등장하는 pat을 찾아서 해당 부분을 pat으로 대체한 문자열을 생성하고 반환합니다.
