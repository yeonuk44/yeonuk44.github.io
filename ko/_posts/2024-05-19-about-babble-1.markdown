---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Babble_1
title: 옹알이 1 (with.Java)
# title: Babble 1 (with.Java)
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
date: 2024-05-19 09:00:00 +0900
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

## "옹알이 1 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 태어난 지 6개월 된 조카를 돌보고 있습니다.

조카는 아직 "aya", "ye", "woo", "ma" 네 가지 발음을 최대 한 번씩 사용해 조합한(이어 붙인) 발음밖에 하지 못합니다.

문자열 배열 babbling이 매개변수로 주어질 때, 머쓱이의 조카가 발음할 수 있는 단어의 개수를 return하도록 solution 함수를 완성해주세요.

#### 제한사항

- 1 ≤ babbling의 길이 ≤ 100
- 1 ≤ babbling[i]의 길이 ≤ 15
- babbling의 각 문자열에서 "aya", "ye", "woo", "ma"는 각각 최대 한 번씩만 등장합니다.
- 즉, 각 문자열의 가능한 모든 부분 문자열 중에서 "aya", "ye", "woo", "ma"가 한 번씩만 등장합니다.
- 문자열은 알파벳 소문자로만 이루어져 있습니다.

#### 입출력 예시

<!-- | lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| babbling                                    | result |
| ------------------------------------------- | ------ |
| ["aya", "yee", "u", "maa", "wyeoo"]         | 1      |
| ["ayaye", "uuuma", "ye", "yemawoo", "ayaa"] | 3      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String[] babbling) {
        int answer = 0;
        String[] vaildBabblings = {"aya", "ye", "woo", "ma"};

        for(String sound : babbling){
            for(String validBabbling : vaildBabblings){
                sound = sound.replace(validBabbling," ");
            }

            sound = sound.replace(" ","");

            if(sound.equals("")){
                answer++;
            }
        }
        return answer;
    }
}
```

### 풀이 리뷰

먼저 유효한 음절 조합을 저장하는 vaildBabblings 배열이 선언됩니다.

이중 반복문을 사용하여 각 문자열(sound)에서 유효한 음절 조합을 제거합니다.

외부 반복문은 입력된 문자열 배열(babbling)을 반복하고, 내부 반복문은 유효한 음절 조합을 반복합니다.

각 유효한 음절 조합을 해당 문자열에서 공백으로 대체합니다.

유효한 음절 조합을 모두 제거한 후에는 문자열에서 공백을 제거합니다.

공백이 모두 제거된 문자열이 빈 문자열("")인 경우에만 answer를 증가시킵니다.

최종적으로 answer를 반환합니다.

이 코드는 입력된 문자열에서 유효한 음절 조합을 찾아 개수를 세는 간단한 방법을 제공합니다.
