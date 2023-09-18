---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Implementing_String_Flipping
title: 문자열 뒤집기 구현에 대하여(with.Java)
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

### 문자열 뒤집기 구현에 대하여(with.Java)

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 my_string과 정수 s, e가 매개변수로 주어질 때, my_string에서 인덱스 s부터 인덱스 e까지를 뒤집은 문자열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| my_string         | s   | e   | result            |
| ----------------- | --- | --- | ----------------- |
| "Progra21Sremm3"  | 6   | 12  | "ProgrammerS123"  |
| "Stanley1yelnatS" | 4   | 10  | "Stanley1yelnatS" |

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    char[] arr;
    public String solution(String my_string, int s, int e) {

        arr = my_string.toCharArray();

        reverse(s,e);
        return new String(arr);
    }

    private void reverse(int startIdx, int endIdx){
        while(startIdx < endIdx){
            char temp = arr[startIdx];
            arr[startIdx++] = arr[endIdx];
            arr[endIdx--] = temp;
        }
    }
}
```

##### 풀이 설명

char[] arr;: 문자열을 문자 배열로 변환하여 저장하기 위한 멤버 변수 arr을 선언합니다.

public String solution(String my_string, int s, int e) : solution 함수는 세 개의 매개변수를 받습니다. my_string은 원본 문자열, s는 뒤집을 부분의 시작 인덱스, e는 뒤집을 부분의 끝 인덱스를 나타냅니다.

arr = my_string.toCharArray();: 주어진 문자열 my_string을 toCharArray 메서드를 사용하여 문자 배열로 변환하고, 이를 arr에 저장합니다.

reverse(s, e);: reverse 메서드를 호출하여 부분 문자열을 뒤집습니다.

private void reverse(int startIdx, int endIdx) : reverse 메서드는 문자 배열의 일부를 뒤집는 역할을 합니다. startIdx와 endIdx 사이의 문자를 뒤집습니다.

while(startIdx < endIdx) : startIdx가 endIdx보다 작을 때까지 루프를 실행합니다.

char temp = arr[startIdx];: 현재 startIdx 위치의 문자를 temp 변수에 임시로 저장합니다.

arr[startIdx++] = arr[endIdx];: startIdx 위치의 문자를 endIdx 위치의 문자로 바꿉니다. 그리고 startIdx를 증가시켜 다음 문자로 이동합니다.

arr[endIdx--] = temp;: endIdx 위치의 문자를 temp에 저장된 값으로 바꿉니다. 그리고 endIdx를 감소시켜 다음 문자로 이동합니다.

return new String(arr);: 뒤집은 문자열을 다시 문자열로 변환하고 반환합니다.

오늘도 좋은 하루 되세요!
