---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_String_Flipping
title: About implementing string flipping (with.Java)
# title: About implementing string flipping (with.Java)

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
date: 2023-09-18 09:00:00 +0900
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

### 글자 지우기, 배열에 존재하는 값에 해당하는 인덱스를 문자열에서 지우는 방법에 대하여(with.Java)

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 my_string과 정수 배열 indices가 주어질 때, my_string에서 indices의 원소에 해당하는 인덱스의 글자를 지우고 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "apporoograpemmemprs"

indices: [1, 16, 6, 15, 0, 10, 11, 3]

result: "programmers"

indices에 있는 인덱스의 글자들을 지우고 이어붙이면 "programmers"가 되므로 이를 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public String solution(String my_string, int[] indices) {
        StringBuilder sb = new StringBuilder(my_string);
        Arrays.sort(indices);
        for(int i = indices.length - 1; i >= 0; i--){
           sb.deleteCharAt(indices[i]);
        }
        return sb.toString();
    }
}
```

##### 풀이 설명

이 코드는 문자열 my_string에서 주어진 정수 배열 indices의 각 원소에 해당하는 인덱스의 문자를 삭제하고, 삭제한 결과 문자열을 반환합니다.

StringBuilder 객체 sb를 생성하여 입력 문자열 my_string의 내용을 복사합니다. StringBuilder는 문자열을 조작하는 데 효율적인 클래스입니다.

Arrays.sort(indices);를 사용하여 indices 배열을 오름차순으로 정렬합니다. 이렇게 하면 삭제할 인덱스들이 낮은 숫자부터 높은 숫자의 순서로 배열됩니다.

반복문을 사용하여 indices 배열의 마지막 원소부터 첫 원소까지 순회합니다. 즉, 높은 인덱스부터 낮은 인덱스로 순회합니다.

sb.deleteCharAt(indices[i]);를 호출하여 indices[i]에 해당하는 인덱스의 문자를 StringBuilder 객체 sb에서 삭제합니다. 높은 인덱스부터 삭제하므로 앞쪽 인덱스의 위치가 바뀌지 않습니다.

모든 인덱스의 문자를 삭제한 후 sb.toString()을 호출하여 StringBuilder 객체의 내용을 문자열로 변환하고 반환합니다.

이렇게 하면 my_string에서 indices 배열에 있는 인덱스의 문자들이 삭제된 문자열이 반환됩니다.

###### 만약 정렬해주지 않고 문자열을 인덱스 따라 삭제하면 어떻게 될까요?

해설에도 약간 힌트를 드렸지만 앞쪽 인덱스가 문자열에서 선삭제가 될 경우 배열에는 삭제된 인덱스를 남은 문자열들이 채워 요소간 위치가 바꿔져서 원하는 결과를 내지 못할 것입니다.

고생하셨습니다.
