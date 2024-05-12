---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Alien_Language_Dictionary
title: 외계어 사전 (with.Java)
# title: Alien language dictionary (with.Java)
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
date: 2024-05-12 09:00:00 +0900
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

## "외계어 사전 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

PROGRAMMERS-962 행성에 불시착한 우주비행사 머쓱이는 외계행성의 언어를 공부하려고 합니다.

알파벳이 담긴 배열 spell과 외계어 사전 dic이 매개변수로 주어집니다.

spell에 담긴 알파벳을 한번씩만 모두 사용한 단어가 dic에 존재한다면 1, 존재하지 않는다면 2를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- spell과 dic의 원소는 알파벳 소문자로만 이루어져있습니다.
- 2 ≤ spell의 크기 ≤ 10
- spell의 원소의 길이는 1입니다.
- 1 ≤ dic의 크기 ≤ 10
- 1 ≤ dic의 원소의 길이 ≤ 10
- spell의 원소를 모두 사용해 단어를 만들어야 합니다.
- spell의 원소를 모두 사용해 만들 수 있는 단어는 dic에 두 개 이상 존재하지 않습니다.
- dic과 spell 모두 중복된 원소를 갖지 않습니다.

#### 입출력 예시

<!-- | keyinput                                  | board    | result  |
| ----------------------------------------- | -------- | ------- |
| ["left", "right", "up", "right", "right"] | [11, 11] | [2, 1]  |
| ["down", "down", "down", "down", "down"]  | [7, 9]   | [0, -4] | -->

| spell                | dic                                     | result |
| -------------------- | --------------------------------------- | ------ |
| ["p", "o", "s"]      | ["sod", "eocd", "qixm", "adio", "soo"]  | 2      |
| ["z", "d", "x"]      | ["def", "dww", "dzx", "loveaw"]         | 1      |
| ["s", "o", "m", "d"] | ["moos", "dzx", "smm", "sunmmo", "som"] | 2      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String[] spell, String[] dic) {
        int answer = 2;
        int count = 0;
        for(String word : dic){
            for(String str : spell){
                if(word.contains(str)){
                    count++;
                }
            }
            System.out.println(count);
            if(count == spell.length){
                answer = 1;
                break;
            }else{
                count = 0;
            }
        }
        return answer;
    }
}
```

### 풀이 설명

answer 변수를 초기값 2로 설정합니다.

이 변수는 결과를 나타냅니다. 2는 초기값으로 설정되어 있습니다.

count 변수를 초기값 0으로 설정합니다.

이 변수는 spell 배열에 있는 단어 중 dic 배열에 포함된 단어의 개수를 세기 위해 사용됩니다.

dic 배열의 각 단어(word)에 대해서 spell 배열의 단어(str)와 비교합니다.

만약 word에 str이 포함되어 있다면, count 변수를 증가시킵니다.
count 변수를 출력합니다.

만약 count 변수가 spell 배열의 길이와 같다면, 모든 단어가 dic 배열에 포함되어 있다는 의미이므로 answer 변수를 1로 설정하고 반복문을 종료합니다.

그렇지 않은 경우, count 변수를 0으로 초기화합니다.

반복문이 모두 종료되면 answer 변수를 반환합니다.

- 장점: 주어진 spell 배열에 있는 모든 단어가 dic 배열에 포함되는지 확인하는 기능을 수행합니다. 코드가 간결하고 이해하기 쉽습니다. count 변수를 사용하여 일치하는 단어의 개수를 세는 방식으로 구현되어 있습니다.
- 단점: 중첩된 반복문을 사용하여 모든 spell과 dic의 단어를 비교하기 때문에 효율성이 낮을 수 있습니다. 시간 복잡도가 증가할 수 있습니다. 중복된 spell 단어가 있는 경우, count 변수가 중복으로 증가하여 잘못된 결과를 출력할 수 있습니다. System.out.println(count)을 사용하여 중간 결과를 출력하는 것은 디버깅 목적으로 사용되는 것으로 보입니다. 실제로는 결과에 영향을 주지 않아야 합니다.
- 개선사항: 중첩된 반복문 대신에 Set 자료구조를 사용하여 중복을 제거하고 일치하는 단어를 찾을 수 있습니다. 이렇게 하면 효율성이 개선됩니다. count 변수 대신에 HashSet을 사용하여 일치하는 단어들을 저장하고, 최종적으로 저장된 단어의 개수와 spell 배열의 길이를 비교하여 결과를 결정할 수 있습니다. 디버깅을 위한 출력문(System.out.println(count))은 제거하거나, 개선된 형태로 사용할 수 있습니다.
