---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Characters_Appear_Only_Once
title: 한 번만 등장한 문자 (with.Java)
# title: Characters that appear only once (with.Java)
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
date: 2024-02-27 09:00:00 +0900
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

## "한 번만 등장한 문자" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

문자열 s가 매개변수로 주어집니다.

s에서 한 번만 등장하는 문자를 사전 순으로 정렬한 문자열을 return 하도록 solution 함수를 완성해보세요.

한 번만 등장하는 문자가 없을 경우 빈 문자열을 return 합니다.

#### 제한사항

- 0 < s의 길이 < 1,000
- s는 소문자로만 이루어져 있습니다.

#### 입출력 예시

| s           | result |
| ----------- | ------ |
| "abcabcadc" | "d"    |
| "abdc"      | "abcd" |
| "hello"     | "eho"  |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public String solution(String s) {
        String answer = "";
        String[] strArr = s.split("");
        int count;
        Arrays.sort(strArr);

        for(String str : strArr){
            count = 0;

            for(int i = 0; i < strArr.length; i++){
                if(strArr[i].equals(str)){
                    count++;
                }
            }

            if(count == 1){
                answer += str;
            }
        }
        return answer;
    }
}
```

### 풀이 설명

- 먼저, 빈 문자열인 answer를 선언합니다. 그리고 주어진 문자열을 각각의 문자로 나눠서 strArr 배열에 저장합니다. 그리고 strArr 배열을 오름차순으로 정렬합니다.
- for-each 문을 사용하여 strArr 배열의 각 요소인 str에 대해서 다음을 수행합니다.
- count 변수를 0으로 초기화합니다.
- for 문을 사용하여 strArr 배열을 순회하면서, 현재 요소와 str이 같은지 비교합니다. 같다면 count를 증가시킵니다.
- count가 1인 경우, 즉 현재 문자가 중복되지 않는 경우에만 answer에 해당 문자를 추가합니다.
- 모든 반복이 완료되면 answer를 반환합니다. 따라서 solution 메서드는 주어진 문자열에서 중복되지 않는 문자들로 이루어진 새로운 문자열을 반환하는 기능을 수행합니다.
