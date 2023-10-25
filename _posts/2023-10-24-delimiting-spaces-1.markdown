---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Delimiting_Spaces_1
title: Delimiting Spaces 1 (with.Java)
# title: Delimiting Spaces 1 (with.Java)
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
date: 2023-10-24 09:00:00 +0900
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

### 문자열 바꿔서 찾는 방법에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자 "A"와 "B"로 이루어진 문자열 myString과 pat가 주어집니다.

myString의 "A"를 "B"로, "B"를 "A"로 바꾼 문자열의 연속하는 부분 문자열 중 pat이 있으면 1을 아니면 0을 return 하는 solution 함수를 완성하세요.

##### 입출력 예시

myString: "ABBAA"

pat: "AABB"

result: 1

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String myString, String pat) {
        int answer = 0;
        char[] ch = new char[myString.length()];
        for(int i = 0; i < myString.length(); i++){
            if(myString.charAt(i) == 'A'){
                ch[i] = 'B';
            }else{
                ch[i] = 'A';
            }
        }
        if(String.valueOf(ch).contains(pat)){
            answer = 1;
        }
        return answer;
    }
}
```

##### 풀이 설명

public int solution(String myString, String pat):

solution 메서드 정의 시작. 이 메서드는 두 개의 문자열 인수 myString과 pat을 받아들이고 정수형 결과를 반환합니다.

int answer = 0;:

answer라는 변수를 선언하고 0으로 초기화합니다. 이 변수는 최종 결과를 저장합니다.

char[] ch = new char[myString.length()];:

myString의 길이와 동일한 길이의 문자 배열 ch를 선언합니다. 이 배열은 myString을 변형하기 위해 사용됩니다.

for(int i = 0; i < myString.length(); i++):

for 루프를 사용하여 myString의 각 문자를 순회합니다.

if(myString.charAt(i) == 'A'){:

현재 인덱스 i의 문자가 'A'인지 확인합니다.

ch[i] = 'B';:

만약 'A'라면, 해당 문자를 'B'로 변환하여 ch 배열에 저장합니다.

}else:

'A'가 아니라면,

ch[i] = 'A';:

해당 문자를 'A'로 변환하여 ch 배열에 저장합니다.

if(String.valueOf(ch).contains(pat)):

ch 배열을 문자열로 변환하고, 변환된 문자열이 pat 문자열을 포함하는지 검사합니다.

answer = 1;:

만약 pat가 ch에 포함되면, answer를 1로 설정합니다.

return answer;:

최종적으로 answer 값을 반환합니다.

이 코드는 myString을 'A'와 'B'로 번갈아가며 변환한 후에 pat 문자열이 포함되어 있는지 확인하는 간단한 문자열 처리 작업을 수행합니다. 결과 값은 1 (포함됨) 또는 0 (포함되지 않음) 중 하나일 것입니다.
