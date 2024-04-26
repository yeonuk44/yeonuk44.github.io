---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Count_Duplicate_Numbers
title: 중복된 숫자 개수(with.Java)
# title: Count duplicate numbers (with.Java)
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
date: 2024-04-26 09:00:00 +0900
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

## "7의 개수(with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 행운의 숫자 7을 가장 좋아합니다.

정수 배열 array가 매개변수로 주어질 때, 7이 총 몇 개 있는지 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

- 1 ≤ array의 길이 ≤ 100
- 0 ≤ array의 원소 ≤ 100,000

#### 입출력 예시

<!-- | my_str             | n   | result                       |
| ------------------ | --- | ---------------------------- |
| "abc1Addfggg4556b" | 6   | ["abc1Ad", "dfggg4", "556b"] |
| "abcdef123"        | 3   | ["abc", "def", "123"]        | -->

| array       | result |
| ----------- | ------ |
| [7, 77, 17] | 4      |
| [10, 29]    | 0      |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int[] array) {
        int answer = 0;
        for(int i = 0; i < array.length; i++){
            String str = String.valueOf(array[i]);
            char[] chArr = str.toCharArray();
            for(char ch : chArr){
                if(ch == '7'){
                    answer += 1;
                }
            }
        }
        return answer;
    }
}
```

### 풀이 설명

1. `public int solution(int[] array)` : solution 메서드는 int 배열을 입력받고, 7의 개수를 반환하는 메서드입니다.
2. `int answer = 0;` : answer 변수를 선언하고 0으로 초기화합니다. 이 변수는 7의 개수를 저장할 변수입니다.
3. `for(int i = 0; i < array.length; i++)` : 배열의 길이만큼 반복하는 반복문입니다. 배열 내의 모든 요소를 하나씩 확인하기 위해 사용됩니다.
4. `String str = String.valueOf(array[i]);` : 배열의 요소를 문자열로 변환합니다. 배열의 요소를 문자열로 변환하는 이유는 해당 숫자가 7인지 확인하기 위해서입니다.
5. `char[] chArr = str.toCharArray();` : 문자열을 문자 배열로 변환합니다. 이렇게 변환한 이유는 문자열을 하나씩 순회하며 7인지 확인하기 위해서입니다.
6. `for(char ch : chArr)` : 문자 배열의 모든 요소를 하나씩 확인하는 반복문입니다.
7. `if(ch == '7')` : 현재 확인하고 있는 문자가 7인지 확인합니다.
8. `answer += 1;` : 문자가 7일 경우, answer 변수에 1을 더합니다. 즉, 7의 개수를 1 증가시킵니다.
9. `return answer;` : 반복문이 끝난 후, 7의 개수를 저장한 answer 변수를 반환합니다.

이렇게 구현된 코드는 주어진 배열에서 7의 개수를 세는 기능을 수행합니다.
