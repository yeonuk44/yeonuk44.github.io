---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_Character_Counting
title: 문자 개수 세기 구현에 대하여(with.Java)
# title: About implementing character counting (with.Java)

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
date: 2023-09-13 09:00:00 +0900
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

### 문자열 여러 번 뒤집기 구현에 대하여(with.Java) 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

어떤 문자열에 대해서 접미사는 특정 인덱스부터 시작하는 문자열을 의미합니다.

예를 들어, "banana"의 모든 접미사는 "banana", "anana", "nana", "ana", "na", "a"입니다.

문자열 my_string과 is_suffix가 주어질 때, is_suffix가 my_string의 접미사라면 1을, 아니면 0을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "banana"

is_suffix: "ana"

result: 1

즉, is_suffix가 my_string의 접미사이기 때문에 1을 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int solution(String my_string, String is_suffix) {
        int answer = 0;
        ArrayList<String> arr = new ArrayList<String>();

        for(int i = 0; i < my_string.length(); i++){
            arr.add(my_string.substring(i));
        }

        answer = arr.contains(is_suffix) ? 1 : 0;
        return answer;
    }
}
```

##### 풀이 설명

모든 접미사를 배열에 저장하기 위해선 한 문자 씩 떼어내 배열에 저장하는 것입니다.

이를 위해 substring()을 사용하여 반복문을 my_string.length()로 접미사 분리해야할 문자열의 길이만큼 순회하여 ArrayList에 삽입했습니다.

이후 is_suffix의 문자열이 arr 요소에 포함된 접미사인지 확인이 필요합니다.

해당 확인을 ArrayList의 contains()를 통해 요소가 있는지 확인 후, 그 참과 거짓에 따라 answer에 값을 담아 출력합니다.
