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

### 접두사인지 확인하는 방법에 대하여(with.Java) 알아본 글입니다.

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

#### 문제

어떤 문자열에 대해서 접두사는 특정 인덱스까지의 문자열을 의미합니다. 예를 들어, "banana"의 모든 접두사는 "b", "ba", "ban", "bana", "banan", "banana"입니다.

문자열 my_string과 is_prefix가 주어질 때, is_prefix가 my_string의 접두사라면 1을, 아니면 0을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "banana"

is_prefix: "ban"

result: 1

즉, is_prefix가 my_string의 접두사이기 때문에 1을 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int solution(String my_string, String is_prefix) {
        int answer = 0;
        ArrayList<String> arr = new ArrayList<String>();
        for(int i = my_string.length(); i > 0; i--){
            arr.add(my_string.substring(0,i));
        }

        answer = arr.contains(is_prefix) ? 1 : 0;
        return answer;
    }
}
```

##### 풀이 설명

이전 글에서 접미사는 제일 마지막 문자가 포함되는 문자열을 하나 씩 만들어 배열에 저장하면 해결되었습니다. 이번엔 접두사에 관련된 문제입니다.

substing()을 다시 알아보면 param을 하나만 입력할 시 startIndex로 인식되어 버려 (startIndex, string length) 형식으로 값을 반환해줍니다.

이번엔 접두사를 만드는 문제이니 startIndex는 항상 0이여야 하며, 마지막 인덱스들이 하나 씩 감소되면 됩니다.

해당 로직에 맞춰 반복문을 순회하도록 초기 값을 my_string.length()로 하고, i 가 0이 되면 순회를 멈추게 하였습니다.

그 이유는 substring(0,0)은 아무것도 반환하지 않게 됩니다. 따라서 0을 포함한채로 반복문이 순회된다면 빈 문자열이 arr에 포함되어 쓸데없는 메모리를 할당받게 됩니다.

이어서 i를 1씩 감소 시키고 answer에 저장된 arr의 요소 중 is_prefix와 동일한 값이 있다면 1을 없다면 0을 반환하게 합니다.
