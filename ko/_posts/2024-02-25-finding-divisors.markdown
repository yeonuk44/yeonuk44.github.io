---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_Divisors
title: 약수 구하기 (with.Java)
# title: Finding divisors (with.Java)
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
date: 2024-02-25 09:00:00 +0900
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

## "문자로 된 숫자를 정수형으로 바꾸기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

영어가 싫은 머쓱이는 영어로 표기되어있는 숫자를 수로 바꾸려고 합니다.

문자열 numbers가 매개변수로 주어질 때, numbers를 정수로 바꿔 return 하도록 solution 함수를 완성해 주세요.

#### 제한사항

- numbers는 소문자로만 구성되어 있습니다.
- numbers는 "zero", "one", "two", "three", "four", "five","six", "seven", "eight", "nine" 들이 공백 없이 조합되어 있습니다.
- 1 ≤ numbers의 길이 ≤ 50
- "zero"는 numbers의 맨 앞에 올 수 없습니다.

#### 입출력 예시

| numbers                                | result    |
| -------------------------------------- | --------- |
| "onetwothreefourfivesixseveneightnine" | 123456789 |
| "onefourzerosixseven"                  | 14067     |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public long solution(String numbers) {
        String string_num = numbers
            .replace("zero", "0")
            .replace("one", "1")
            .replace("two", "2")
            .replace("three", "3")
            .replace("four", "4")
            .replace("five", "5")
            .replace("six", "6")
            .replace("seven", "7")
            .replace("eight", "8")
            .replace("nine", "9");

        long answer = Long.parseLong(string_num);
        return answer;
    }
}
```

### 풀이 설명

- 문자열 numbers에서 replace 메소드를 사용해 영어로 된 숫자를 대응되는 실제 숫자로 바꿉니다. replace 메소드는 첫 번째 인자로 받은 문자열을 두 번째 인자로 받은 문자열로 모두 바꾸는 역할을 합니다. 이렇게 해서 "zero"는 "0", "one"은 "1" 등으로 바뀝니다.
- 변환된 문자열 string_num은 실제 숫자 형태의 문자열이므로, Long.parseLong 메소드를 통해 long 타입의 숫자로 변환됩니다. 이 변환된 long 타입의 숫자가 최종 결과로 반환됩니다.
- 이 메소드는 영어로 표현된 숫자를 실제 숫자로 변환하는 역할을 합니다. 예를 들어, "onetwothree"라는 입력이 들어오면 "123"으로 변환 후, 이를 숫자 123으로 변환하여 반환합니다.
- 각 문자에 대해 아스키 코드 값을 기반으로 판단하며, 아스키 코드에서 65 ~ 90은 대문자 A ~ Z를 나타냅니다. 따라서 이 범위에 해당하는 문자는 소문자로 변환하고, 그렇지 않은 문자(즉, 소문자)는 대문자로 변환합니다.
- char형을 사용하는 이유는 아스키 코드를 이용해서 문자의 대소문자를 판별하기에 적합하기 때문입니다. char형은 숫자로 변환할 수 있으니 이런 식으로 아스키 코드를 활용할 수 있습니다. 반면에 String 형은 문자열 전체에 대한 값이므로 아스키 코드를 직접적으로 활용하는 것이 불가능합니다.
- toUpperCase나 toLowerCase 같은 메서드는 String 클래스의 메서드이기 때문에 String 객체에서만 사용 가능합니다. char형에는 이와 같은 메서드가 없기 때문에, 대소문자 변환을 위해 ch형을 String형으로 변환한 후 사용합니다. 이 변환은 Character.toString(ch)를 통해 이루어집니다.
