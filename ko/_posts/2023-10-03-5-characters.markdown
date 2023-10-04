---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_5_Characters
title: 5명씩, 주어진 문자열 리스트를 5명씩 끊어서 제일 앞의 문자만 모아 배열로 출력하는 방법에 대하여(with.Java)
# title: How to truncate a given list of strings by 5 characters, collecting only the first character and outputting it to an array.

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
date: 2023-10-03 09:00:00 +0900
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

### 할 일 목록(with.Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

오늘 해야 할 일이 담긴 문자열 배열 todo_list와 각각의 일을 지금 마쳤는지를 나타내는 boolean 배열 finished가 매개변수로 주어질 때, todo_list에서 아직 마치지 못한 일들을 순서대로 담은 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| todo_list                                                  | finished                   | result                           |
| ---------------------------------------------------------- | -------------------------- | -------------------------------- |
| ["problemsolving", "practiceguitar", "swim", "studygraph"] | [true, false, true, false] | ["practiceguitar", "studygraph"] |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public String[] solution(String[] todo_list, boolean[] finished) {
        ArrayList<String> answer = new ArrayList<String>();

        for(int i = 0; i < finished.length; i++){
            if(finished[i] == false){
                answer.add(todo_list[i]);
            }
        }
        String[] result = new String[answer.size()];
        for(int j = 0; j < answer.size(); j++){
            result[j] = answer.get(j);
        }
        return result;
    }
}
```

##### 풀이 설명

ArrayList<String> answer = new ArrayList<String>();: 아직 완료되지 않은 할 일 목록을 저장하기 위한 문자열 ArrayList answer를 생성합니다.

for(int i = 0; i < finished.length; i++) : finished 배열을 반복하면서 각 할 일의 완료 여부를 검사합니다.

if(finished[i] == false) : 만약 현재 할 일이 완료되지 않았다면 (즉, finished[i]가 false이면), 해당 할 일을 answer ArrayList에 추가합니다.

String[] result = new String[answer.size()];: answer ArrayList의 크기에 맞는 문자열 배열 result를 생성합니다.

for(int j = 0; j < answer.size(); j++) : answer ArrayList를 반복하면서 각 할 일을 result 배열에 복사합니다.

return result;: 최종적으로 아직 완료되지 않은 할 일 목록이 담긴 result 배열을 반환합니다.
