---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Three_Delimiters
title: 세 개의 구분자(with.Java)
# title: Three delimiters (with.Java)
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
date: 2023-10-22 09:00:00 +0900
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

### 세 개의 구분자로 문자열을 나누는 방법에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

임의의 문자열이 주어졌을 때 문자 "a", "b", "c"를 구분자로 사용해 문자열을 나누고자 합니다.

예를 들어 주어진 문자열이 "baconlettucetomato"라면 나눠진 문자열 목록은 ["onlettu", "etom", "to"] 가 됩니다.

문자열 myStr이 주어졌을 때 위 예시와 같이 "a", "b", "c"를 사용해 나눠진 문자열을 순서대로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.

단, 두 구분자 사이에 다른 문자가 없을 경우에는 아무것도 저장하지 않으며, return할 배열이 빈 배열이라면 ["EMPTY"]를 return 합니다.

##### 입출력 예시

| myStr                | result                    |
| -------------------- | ------------------------- |
| "baconlettucetomato" | ["onlettu", "etom", "to"] |
| "abcd"               | ["d"]                     |
| "cabab"              | ["EMPTY"]                 |

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String[] solution(String myStr) {
        StringBuilder str = new StringBuilder("");
        boolean insideWord = false;
        for(int i = 0; i < myStr.length(); i++){
            if(myStr.charAt(i) == 'a' || myStr.charAt(i) == 'b' || myStr.charAt(i) == 'c'){
                if (insideWord) {
                    str.append(' ');
                    insideWord = false;
                }
            } else{
                str.append(myStr.charAt(i));
                insideWord = true;
            }
        }
        if(str.length() == 0){
            str.append("EMPTY");
        }
        String[] answer = str.toString().split(" ");
        return answer;
    }
}
```

##### 풀이 설명

주요 로직은 입력 문자열 myStr을 반복하여 각 문자를 검사하고, 'a', 'b', 'c' 문자를 만나면 해당 문자를 제거하고 단어를 분리하는 것입니다.

insideWord 변수를 사용하여 현재 단어 내부에 있는지 여부를 추적합니다.

StringBuilder 객체 str을 사용하여 문자열을 동적으로 빌드합니다.

StringBuilder 클래스의 append(char c) 메서드: 문자열 빌더에 문자를 추가합니다.

StringBuilder 클래스의 toString() 메서드: StringBuilder 객체를 문자열로 변환합니다.

String 클래스의 split(String regex) 메서드: 문자열을 정규식 패턴 또는 구분자로 분할하고 문자열 배열로 반환합니다.
