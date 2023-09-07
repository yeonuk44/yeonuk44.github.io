---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Concatenate_Substring_To_Create_A_String
title: 부분 문자열 이어 붙여 문자열 만드는 방법에 대하여(with.Java)
# title: How to concatenate substring to create a string (with.Java)

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
date: 2023-09-07 09:00:00 +0900
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

### 접미사 배열 구현에 대하여(with.Java) 알아본 글입니다.

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.
문제에 대해 먼저 알아보겠습니다.

#### 문제

어떤 문자열에 대해서 접미사는 특정 인덱스부터 시작하는 문자열을 의미합니다.
예를 들어, "banana"의 모든 접미사는 "banana", "anana", "nana", "ana", "na", "a"입니다.
문자열 my_string이 매개변수로 주어질 때, my_string의 모든 접미사를 사전순으로 정렬한 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "banana"
result: ["a", "ana", "anana", "banana", "na", "nana"]

즉, my_string는 "banana"로 모든 접미사는 문제의 설명과 같습니다.
이를 사전순으로 정렬하면 "a", "ana", "anana", "banana", "na", "nana"이므로 ["a", "ana", "anana", "banana", "na", "nana"]를 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public String[] solution(String my_string) {
        ArrayList<String> arr = new ArrayList<String>();
        for(int i = 0; i < my_string.length(); i++){
            arr.add(my_string.substring(i));
        }
        Collections.sort(arr);
        String[] answer = new String[arr.size()];
        for(int j = 0; j < arr.size(); j++){
            answer[j] = arr.get(j);
        }
        return answer;
    }
}
```

##### 풀이 설명

모든 접미사를 배열에 저장하기 위해선 한 문자 씩 떼어내 배열에 저장하는 것입니다.
이를 위해 substring()을 사용하여 반복문을 my_string.length()로 접미사 분리해야할 문자열의 길이만큼 순회하여 ArrayList에 삽입했습니다.
이렇게만 해도 사실 모든 접미사는 구별이 끝났습니다. 그러나 요구되는 결과에는 모든 접미사를 사전편찬 순으로 정렬하길 바랬기에 Collections의 sort()를 통해 arr 안의 요소들을 정렬해줬습니다.
