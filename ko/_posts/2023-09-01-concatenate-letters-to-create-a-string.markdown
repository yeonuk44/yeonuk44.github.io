---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Concatenate_Letters_To_Create_A_String
title: 글자 이어 붙여 문자열 만드는 방법에 대하여(with.Java)
# title: How to concatenate letters to create a string (with.Java)
# concatenate letters to create a string

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
date: 2023-09-01 09:00:00 +0900
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

### 글자 이어 붙여 문자열 만드는 방법에 대하여(with.Java)

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.
문제에 대해 먼저 알아보겠습니다.

#### 문제

문자열 my_string과 정수 배열 index_list가 매개변수로 주어집니다. my_string의 index_list의 원소들에 해당하는 인덱스의 글자들을 순서대로 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "cvsgiorszzzmrpaqpe"
index_list: [16, 6, 5, 3, 12, 14, 11, 11, 17, 12, 7]
result: "programmers"

예제 1번의 my_string에서 인덱스 3, 5, 6, 11, 12, 14, 16, 17에 해당하는 글자는 각각 g, o, r, m, r, a, p, e이므로 my_string에서 index_list에 들어있는 원소에 해당하는 인덱스의 글자들은 각각 순서대로 p, r, o, g, r, a, m, m, e, r, s입니다. 따라서 "programmers"를 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public String solution(String my_string, int[] index_list) {
        String answer = "";
        ArrayList<Character> arr = new ArrayList<Character>();

        for(int i = 0; i < index_list.length; i++){
            arr.add(my_string.charAt(index_list[i]));
        }
        for(int j = 0; j < arr.size(); j++){
            answer += arr.get(j);
        }
        return answer;
    }
}
```

##### 풀이 설명

해당 코드는 my_string에서 index_list의 요소를 순차적으로 추출하여 저장해 출력하면 되는 문제입니다.
따라서 문자열에서 인덱싱을 할 필요가 있습니다. 이에 ArrayList인 arr배열을 Character로 생성하여 문자열을 index로 한개 씩 가져옵니다.
때문에 .charAt() 함수를 사용해 my_string을 하나씩 인덱스 별로 추출해서 저장합니다. 이후 answer엔 character 타입의 arr를 반복문을 통해 저장합니다.
