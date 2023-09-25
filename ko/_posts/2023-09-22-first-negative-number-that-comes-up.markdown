---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_First_Negative_Number_That_Comes_Up
title: 첫 번째로 나오는 음수(with.Java)
# title: The first negative number that comes up (with.Java)

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
date: 2023-09-22 09:00:00 +0900
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

### 첫 번째로 나오는 음수(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 리스트 num_list가 주어질 때, 첫 번째로 나오는 음수의 인덱스를 return하도록 solution 함수를 완성해주세요. 음수가 없다면 -1을 return합니다.

##### 입출력 예시

| num_list                    | result |
| --------------------------- | ------ |
| [12, 4, 15, 46, 38, -2, 15] | 5      |
| [13, 22, 53, 24, 15, 6]     | -1     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;
        for(int i = 0; i < num_list.length; i++){
            if(num_list[i] < 0){
                answer = i;
                break;
            } else answer = -1;
        }
        return answer;
    }
}
```

##### 풀이 설명

int answer = 0;: 반환할 결과값을 저장할 변수 answer를 초기화합니다. answer가 0으로 초기화되어 있으며, 이는 음수 값이 발견되지 않았을 때의 기본값입니다.

for(int i = 0; i < num_list.length; i++): 배열 num_list를 반복하면서 각 요소를 검사합니다.

if(num_list[i] < 0): 현재 요소가 음수인지 검사합니다.

answer = i;: 음수 값이 발견되면 현재 인덱스 i를 answer에 저장하고 반복문을 종료합니다.

break;: 음수 값이 발견되면 반복문을 종료합니다.

else answer = -1;: 음수 값이 발견되지 않으면 answer를 -1로 설정합니다. 이는 음수 값이 배열에 없을 때를 나타냅니다.

return answer;: 최종적으로 answer를 반환합니다. 이는 배열에서 첫 번째로 발견된 음수 값의 인덱스이거나, 음수 값이 없으면 -1이 반환됩니다.
