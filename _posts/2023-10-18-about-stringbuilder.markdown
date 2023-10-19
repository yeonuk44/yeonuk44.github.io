---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_StringBuilder
title: Why StringBuilder is efficient
# title: Why StringBuilder is efficient
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
date: 2023-10-18 09:00:00 +0900
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

### 문자열 잘라서 정렬하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 myString이 주어집니다.

"x"를 기준으로 해당 문자열을 잘라내 배열을 만든 후 사전순으로 정렬한 배열을 return 하는 solution 함수를 완성해 주세요.

단, 빈 문자열은 반환할 배열에 넣지 않습니다.

##### 입출력 예시

myString: "axbxcxdx"

result: ["a","b","c","d"]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public String[] solution(String myString) {

        ArrayList<String> arr = new ArrayList<String>();
        String str = "";
        for(int i = 0; i < myString.length(); i++){
            if(myString.charAt(i) == 'x'){
                arr.add(str);
                str = "";
            }else{
                str += myString.charAt(i);
            }
        }

        if (!str.isEmpty()) {
            arr.add(str);
        }

        arr.removeIf(String::isEmpty);
        Collections.sort(arr);

        String[] answer = new String[arr.size()];
        for(int j = 0; j < answer.length; j++){
            answer[j] = arr.get(j);
        }
        return answer;
    }
}
```

##### 풀이 설명

ArrayList<String> arr = new ArrayList<String>();: 부분 문자열을 저장할 ArrayList인 arr을 생성합니다.

String str = "";: 현재 부분 문자열을 저장할 빈 문자열 str을 생성합니다.

for(int i = 0; i < myString.length(); i++) { ... }: 주어진 문자열 myString을 한 글자씩 순회하는 반복문을 시작합니다.

if(myString.charAt(i) == 'x') { ... }: 현재 문자가 "x"인지 확인합니다. 만약 "x"라면 현재까지의 부분 문자열 str을 arr 리스트에 추가하고 str을 초기화합니다.

그렇지 않은 경우에는 str에 현재 문자를 추가합니다.

반복문을 통해 문자열을 순회하면서 "x"를 기준으로 부분 문자열을 추출하고 arr 리스트에 저장합니다.

if (!str.isEmpty()) { arr.add(str); }: 마지막 부분 문자열 처리를 위해, 만약 str이 비어 있지 않다면 이를 arr 리스트에 추가합니다.

arr.removeIf(String::isEmpty);: 빈 문자열을 removeIf 메소드를 사용하여 arr 리스트에서 제거합니다.

Collections.sort(arr);: arr 리스트를 사전순으로 정렬합니다.

String[] answer = new String[arr.size()];: 길이가 결정된 arr 리스트를 기반으로 결과 배열 answer를 생성합니다.

for(int j = 0; j < answer.length; j++) { ... }: arr 리스트에 저장된 부분 문자열을 answer 배열로 복사합니다.

함수가 종료되고 answer 배열을 반환합니다. 이 배열에는 "x"를 기준으로 분리된 부분 문자열이 빈 문자열을 제외하고 사전순으로 정렬되어 있습니다.
