---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Left_Right
title: 왼쪽 오른쪽(with.Java)
# title: Left Right (with.Java)

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
date: 2023-09-28 09:00:00 +0900
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

### 왼쪽 오른쪽(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 리스트 str_list에는 "u", "d", "l", "r" 네 개의 문자열이 여러 개 저장되어 있습니다.

str_list에서 "l"과 "r" 중 먼저 나오는 문자열이 "l"이라면 해당 문자열을 기준으로 왼쪽에 있는 문자열들을 순서대로 담은 리스트를, 먼저 나오는 문자열이 "r"이라면 해당 문자열을 기준으로 오른쪽에 있는 문자열들을 순서대로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

"l"이나 "r"이 없다면 빈 리스트를 return합니다.

##### 입출력 예시

| str_list             | result     |
| -------------------- | ---------- |
| ["u", "u", "l", "r"] | ["u", "u"] |
| ["l"]                | []         |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String[] solution(String[] str_list) {
        int lIndex = -1;
        int rIndex = -1;

        for (int i = 0; i < str_list.length; i++) {
            if (str_list[i].equals("l")) {
                lIndex = i;
                break;
            } else if (str_list[i].equals("r")) {
                rIndex = i;
                break;
            }
        }
        if (lIndex == -1 && rIndex == -1) {
            return new String[0];
        }

        if (lIndex != -1) {
            String[] answer = new String[lIndex];
            for (int j = 0; j < lIndex; j++) {
                answer[j] = str_list[j];
            }
            return answer;
        }
        else {
            String[] answer = new String[str_list.length - rIndex - 1];
            for (int k = rIndex + 1; k < str_list.length; k++) {
                answer[k - rIndex - 1] = str_list[k];
            }
            return answer;
        }
    }
}
```

##### 풀이 설명

int lIndex = -1;, int rIndex = -1;: "l" 문자의 인덱스와 "r" 문자의 인덱스를 초기화합니다. 초기값은 -1로 설정되어 있습니다.

첫 번째 반복문(for (int i = 0; i < str_list.length; i++) {): 배열 str_list를 반복하면서 "l" 또는 "r" 문자를 찾습니다. 만약 "l"을 찾으면 lIndex에 해당 인덱스를 저장하고 반복문을 종료하고, "r"을 찾으면 rIndex에 해당 인덱스를 저장하고 반복문을 종료합니다.

if (lIndex == -1 && rIndex == -1) { return new String[0]; }: "l"과 "r" 모두 찾지 못한 경우, 빈 문자열 배열을 반환합니다.

if (lIndex != -1) { ... } else { ... }: "l" 또는 "r" 중 하나를 찾은 경우에 따라 다른 로직을 수행합니다.

"l"을 찾은 경우:

String[] answer = new String[lIndex];: "l" 문자 이전의 문자열을 저장할 배열 answer를 생성합니다.

반복문을 사용하여 "l" 문자 이전의 문자열을 answer 배열에 복사합니다.

answer 배열을 반환합니다.

"r"을 찾은 경우:

String[] answer = new String[str_list.length - rIndex - 1];: "r" 문자 이후의 문자열을 저장할 배열 answer를 생성합니다.

반복문을 사용하여 "r" 문자 이후의 문자열을 answer 배열에 복사합니다.

answer 배열을 반환합니다.
