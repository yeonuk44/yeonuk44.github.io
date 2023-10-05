---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Length_Operations
title: 길이에 따른 연산(with.Java)
# title: Length-based operations (with.Java)

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
date: 2023-10-04 09:00:00 +0900
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

### 5명씩, 주어진 문자열 리스트를 5명씩 끊어서 제일 앞의 문자만 모아 배열로 출력하는 방법에 대하여(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

최대 5명씩 탑승가능한 놀이기구를 타기 위해 줄을 서있는 사람들의 이름이 담긴 문자열 리스트 names가 주어질 때, 앞에서 부터 5명씩 묶은 그룹의 가장 앞에 서있는 사람들의 이름을 담은 리스트를 return하도록 solution 함수를 완성해주세요.

마지막 그룹이 5명이 되지 않더라도 가장 앞에 있는 사람의 이름을 포함합니다.

##### 입출력 예시

names: ["nami", "ahri", "jayce", "garen", "ivern", "vex", "jinx"]

result: ["nami", "vex"]

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public String[] solution(String[] names) {
        String[] answer = new String[(int)Math.ceil(names.length / 5.0)];
        int count = 0;
        for(int i = 0; i < names.length; i += 5){
            answer[count++] = names[i];
        }
        return answer;
    }
}
```

##### 풀이 설명

함수의 반환 타입은 String[]이며, names라는 문자열 배열을 인자로 받습니다.

answer 배열을 생성하며, 그룹의 개수를 계산하여 배열 크기를 결정합니다. count 변수는 answer 배열에 값을 넣을 때 사용됩니다.주의할 점은 Java에서 정수끼리의 나눗셈은 결과가 정수로 반환되어 소수 부분이 버려지기 때문에, 예상과 다른 결과가 발생할 수 있습니다.

그렇기 때문에 그룹의 개수를 계산할 때 실수형으로 나누어야 정확한 값을 얻을 수 있습니다. 때문에 5.0으로 올림처리를 해주었습니다.

반복문을 통해 각 그룹을 처리합니다. i 변수는 현재 그룹의 시작 인덱스를 나타내고, groupSize 변수는 현재 그룹의 크기를 결정합니다.

그룹에 속하는 사람들의 이름을 groupNames에 추가합니다. i + j를 통해 실제 인원들의 인덱스를 찾아서 이름을 가져옵니다.

각 그룹의 이름을 하나의 문자열로 만들어 answer 배열에 저장합니다. 문자열의 앞뒤 공백을 제거한 후 저장합니다.

완성된 answer 배열을 반환하여 함수의 결과로 제공합니다.
