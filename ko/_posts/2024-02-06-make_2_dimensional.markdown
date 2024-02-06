---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Make_2_Dimensional
title: 2차원으로 만들기 (with.Java)
# title: Making it two-dimensional (with.Java)
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
date: 2024-02-06 09:00:00 +0900
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

## "모스부호 1" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 친구에게 모스부호를 이용한 편지를 받았습니다.

그냥은 읽을 수 없어 이를 해독하는 프로그램을 만들려고 합니다.

문자열 letter가 매개변수로 주어질 때, letter를 영어 소문자로 바꾼 문자열을 return 하도록 solution 함수를 완성해보세요.

모스부호는 다음과 같습니다.

```java
morse = {
'.-':'a','-...':'b','-.-.':'c','-..':'d','.':'e','..-.':'f',
'--.':'g','....':'h','..':'i','.---':'j','-.-':'k','.-..':'l',
'--':'m','-.':'n','---':'o','.--.':'p','--.-':'q','.-.':'r',
'...':'s','-':'t','..-':'u','...-':'v','.--':'w','-..-':'x',
'-.--':'y','--..':'z'
}
```

#### 제한사항

- 1 ≤ letter의 길이 ≤ 1,000
- return값은 소문자입니다.
- letter의 모스부호는 공백으로 나누어져 있습니다.
- letter에 공백은 연속으로 두 개 이상 존재하지 않습니다.
- 해독할 수 없는 편지는 주어지지 않습니다.
- 편지의 시작과 끝에는 공백이 없습니다.

#### 입출력 예시

| letter                    | result   |
| ------------------------- | -------- |
| ".... . .-.. .-.. ---"    | "hello"  |
| ".--. -.-- - .... --- -." | "python" |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String letter) {
        String[] morseArray = letter.split(" ");
        StringBuilder answer = new StringBuilder();
        String[] morseAlphabet = {
            ".-", "-...", "-.-.", "-..", ".", "..-.", "--.", "....", "..", ".---",
            "-.-", ".-..", "--", "-.", "---", ".--.", "--.-", ".-.", "...", "-",
            "..-", "...-", ".--", "-..-", "-.--", "--.."
        };

        for (String morse : morseArray){
            for (int i = 0; i < morseAlphabet.length; i++) {
                if (morse.equals(morseAlphabet[i])) {
                    char decodedChar = (char) ('a' + i);
                    answer.append(decodedChar);
                }
            }
        }

        return answer.toString();
    }
}
```

### 풀이 설명

split: 문자열을 공백을 기준으로 나누어 배열로 만듭니다.

여기서는 Morse 코드를 공백을 기준으로 나누어 배열로 저장하고 있습니다.

(char) ('a' + i): ASCII 코드를 활용하여 i 값을 알파벳으로 변환하고 있습니다. 'a' + i는 i가 0일 때 'a'를 반환하고, i가 1일 때 'b'를 반환하는 식으로 동작합니다.

**왜 (char) ('a' + i)를 사용했는가**
i 값에 따라 'a'에서부터 차례로 알파벳을 얻기 위해 사용됩니다.

(char)는 정수를 문자로 변환하는 캐스팅을 의미하며, 'a' + i는 ASCII 코드에서 i에 해당하는 알파벳을 얻기 위한 표현식입니다.

이를 통해 Morse 코드를 알파벳으로 변환하고 그 결과를 StringBuilder를 사용하여 최종 문자열로 만들고 있습니다.

Java에서는 배열의 인덱스를 사용하여 각각의 값을 직접 매핑하는 방식을 사용할 수 있습니다.

그러나 여러 가지 이유로 매핑이 필요한 경우, HashMap 또는 다른 매핑 구조를 사용하는 것이 편리할 수 있습니다.

**HashMap을 사용할 경우**

- 동적인 매핑: 새로운 알파벳이나 Morse 코드가 추가되거나 변경될 수 있는 경우, HashMap을 사용하면 동적으로 매핑을 조정할 수 있습니다.
- 키-값 쌍 관리: HashMap을 사용하면 키와 값의 쌍을 쉽게 추가, 삭제, 수정할 수 있습니다.

#### 예시:

```java
// 초기화 블록을 사용하여 HashMap 초기화
    static {
        morseMap = new HashMap<>();
        morseMap.put(".-", 'a');
        morseMap.put("-...", 'b');
        morseMap.put("-.-.", 'c');
        ...
     }
```

**배열을 사용하는 경우**

- 정적인 매핑: 매핑이 변경되지 않고 고정된 경우 배열을 사용할 수 있습니다.
- 간단한 구조: 매핑이 간단하고 변경될 가능성이 낮은 경우 배열을 사용하여 코드를 간결하게 유지할 수 있습니다.

따라서 상황에 따라 적절한 데이터 구조를 선택하는 것이 중요합니다. 각각의 장단점을 고려하여 코드를 작성하면 됩니다.
