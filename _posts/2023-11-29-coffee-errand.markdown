---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Coffee_Errand
title: Coffee Errand (with.Java)
# title: Coffee Errand (with.Java)
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
date: 2023-11-29 09:00:00 +0900
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

## "그림 확대" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

직사각형 형태의 그림 파일이 있고, 이 그림 파일은 1 × 1 크기의 정사각형 크기의 픽셀로 이루어져 있습니다.

이 그림 파일을 나타낸 문자열 배열 picture과 정수 k가 매개변수로 주어질 때, 이 그림 파일을 가로 세로로 k배 늘린 그림 파일을 나타내도록 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

#### 입출력 예시

| picture               | k   | result                                                                                                                |
| --------------------- | --- | --------------------------------------------------------------------------------------------------------------------- |
| ["x.x", ".x.", "x.x"] | 3   | ["xxx...xxx", "xxx...xxx", "xxx...xxx", "...xxx...", "...xxx...", "...xxx...", "xxx...xxx", "xxx...xxx", "xxx...xxx"] |

### 문제에 대한 나의 풀이

```java
class Solution {
    public String[] solution(String[] picture, int k) {
        int rows = picture.length;
        int cols = picture[0].length();

        String[] answer = new String[rows * k];

        StringBuilder tempStr = new StringBuilder();
        int count = 0;

        for (String str : picture) {
            for (int i = 0; i < str.length(); i++) {
                char ch = str.charAt(i);
                for (int j = 0; j < k; j++) {
                    tempStr.append(ch);
                }
            }

            for (int j = 0; j < k; j++) {
                answer[count++] = tempStr.toString();
            }

            tempStr.setLength(0);
        }

        return answer;
    }
}
```

#### 풀이 설명

int rows = picture.length;와 int cols = picture[0].length();: 주어진 picture 배열의 행과 열 수를 계산합니다.

String[] answer = new String[rows * k];: 결과를 저장할 새로운 문자열 배열 answer를 생성합니다. 배열의 크기는 rows \* k가 됩니다.

StringBuilder tempStr = new StringBuilder();: 임시 문자열을 저장하기 위한 StringBuilder 객체 tempStr을 생성합니다.

int count = 0;: 결과 배열 answer의 인덱스를 추적하기 위한 변수 count를 초기화합니다.

for (String str : picture) : 주어진 picture 배열의 각 문자열 str에 대해 반복합니다.

for (int i = 0; i < str.length(); i++) : 각 문자열 str의 문자를 반복하면서:

문자 ch를 가져옵니다.
해당 문자 ch를 k번 반복하여 tempStr에 추가합니다.
for (int j = 0; j < k; j++) : 문자열 tempStr을 k번 반복하여 answer 배열에 추가합니다.

tempStr.setLength(0);: 임시 문자열 tempStr을 비워줍니다.

return answer;: 새로 생성된 문자열 배열 answer를 반환합니다.
